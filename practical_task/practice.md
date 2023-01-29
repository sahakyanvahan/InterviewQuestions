<h1 align="center">Practical Task</h1>

<br/><br/>

## 1. Please write some service that has method for getting a list of employees from some external source.
## Make it asyncronous
## Use dependency injection
## Add unit tests
### Answer
> The code block

* **From external api**
``` C#
using System.Collections.Generic;
using System.Net.Http;
using Newtonsoft.Json;

public class EmployeeService
{
    private readonly HttpClient _httpClient;

    public EmployeeService()
    {
        _httpClient = new HttpClient();
    }

    public async Task<List<Employee>> GetEmployeesAsync()
    {
        var response = await _httpClient.GetAsync("https://example.com/employees");
        var json = await response.Content.ReadAsStringAsync();
        return JsonConvert.DeserializeObject<List<Employee>>(json);
    }
}
```

* **From Database**
```C#
using System.Collections.Generic;
using System.Linq;
using Microsoft.EntityFrameworkCore;

public class EmployeeService
{
    private readonly IEmployeeRepository employeeRepository;

    public EmployeeService(IEmployeeRepository employeeRepository)
    {
        this.employeeRepository = employeeRepository;
    }

    public List<Employee> GetEmployees()
    {
        return employeeRepository.GetAll().ToList();
    }
}

public interface IEmployeeRepository
{
    IQueryable<Employee> GetAll();
}

public class EmployeeRepository : IEmployeeRepository
{
    private readonly EmployeeDbContext dbContext;

    public EmployeeRepository(EmployeeDbContext dbContext)
    {
        this.dbContext = dbContext;
    }

    public IQueryable<Employee> GetAll()
    {
        return dbContext.Employees;
    }
}

public class EmployeeDbContext : DbContext
{
    public DbSet<Employee> Employees { get; set; }

    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        optionsBuilder.UseSqlServer("Data Source=localhost;Initial Catalog=EmployeeDB;Integrated Security=True");
    }
}

public class Employee
{
    public int Id { get; set; }
    public string Name { get; set; }
    public decimal Salary { get; set; }
    public string Department { get; set; }
}
```

* **Unit Tests**
```C#
using Moq;
using System.Linq;
using Xunit;

public class EmployeeServiceTests
{
    [Fact]
    public void GetEmployees_ReturnsAllEmployees()
    {
        // Arrange
        var employees = new List<Employee>
        {
            new Employee { Id = 1, Name = "John Smith", Salary = 50000, Department = "IT" },
            new Employee { Id = 2, Name = "Jane Doe", Salary = 60000, Department = "HR" },
            new Employee { Id = 3, Name = "Bob Johnson", Salary = 55000, Department = "Marketing" },
        };

        var mockRepository = new Mock<IEmployeeRepository>();
        mockRepository.Setup(repo => repo.GetAll()).Returns(employees.AsQueryable());

        var service = new EmployeeService(mockRepository.Object);

        // Act
        var result = service.GetEmployees();

        // Assert
        Assert.Equal(employees, result);
    }

    [Fact]
    public void GetEmployees_ReturnsEmptyList_WhenNoEmployeesInRepository()
    {
        // Arrange
        var mockRepository = new Mock<IEmployeeRepository>();
        mockRepository.Setup(repo => repo.GetAll()).Returns(Enumerable.Empty<Employee>().AsQueryable());

        var service = new EmployeeService(mockRepository.Object);

        // Act
        var result = service.GetEmployees();

        // Assert
        Assert.Empty(result);
    }
}
```

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Should write                | Maybe minor issues. Problems with unit tests |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | No Problems     |
---
<br/><br/>

## 2. Imagine you have an application for managing employees in your organization. Please write a controller method for creating a new employee. It should include validation. 
## Make it asyncronous
## Use dependency injection
## Add unit tests
## Asume you are using CQRS pattern

### Answer
* **The code block with controller and `Data Annotation` based validation**

``` C#
using System.Threading.Tasks;
using Microsoft.AspNetCore.Mvc;

[Route("api/[controller]")]
public class EmployeeController : Controller
{
    private readonly ICommandBus _commandBus;

    public EmployeeController(ICommandBus commandBus)
    {
        _commandBus = commandBus;
    }

    [HttpPost]
    public async Task<IActionResult> Create([FromBody] CreateEmployeeCommand command)
    {
        if (!ModelState.IsValid)
        {
            return BadRequest(ModelState);
        }

        await _commandBus.Send(command);

        return CreatedAtAction(nameof(Get), new { id = command.Id }, command);
    }
}

public class CreateEmployeeCommand : ICommand
{
    public int Id { get; set; }
    public string Name { get; set; }
    public decimal Salary { get; set; }
    public string Department { get; set; }

    [Required]
    public string Email { get; set; }
}

public class CreateEmployeeCommandHandler : ICommandHandler<CreateEmployeeCommand>
{
    private readonly EmployeeDbContext dbContext;

    public CreateEmployeeCommandHandler(EmployeeDbContext dbContext)
    {
        this.dbContext = dbContext;
    }

    public async Task HandleAsync(CreateEmployeeCommand command)
    {
        var employee = new Employee
        {
            Id = command.Id,
            Name = command.Name,
            Salary = command.Salary,
            Department = command.Department,
            Email = command.Email
        };

        dbContext.Employees.Add(employee);
        await dbContext.SaveChangesAsync();
    }
}
```

> * **Same with `Fluent Validation`**
```C#
using FluentValidation;
using Microsoft.AspNetCore.Mvc;

public class EmployeeController : ControllerBase
{
    private readonly ICommandDispatcher commandDispatcher;
    private readonly IValidator<CreateEmployeeCommand> validator;

    public EmployeeController(ICommandDispatcher commandDispatcher, IValidator<CreateEmployeeCommand> validator)
    {
        this.commandDispatcher = commandDispatcher;
        this.validator = validator;
    }

    [HttpPost]
    public async Task<IActionResult> Create(CreateEmployeeCommand command)
    {
        var validationResult = await validator.ValidateAsync(command);

        if (!validationResult.IsValid)
        {
            foreach (var error in validationResult.Errors)
            {
                ModelState.AddModelError(error.PropertyName, error.ErrorMessage);
            }

            return BadRequest(ModelState);
        }

        await commandDispatcher.DispatchAsync(command);
        return CreatedAtAction(nameof(Get), new { id = command.Id }, command);
    }
    //other methods
}

using FluentValidation;

public class CreateEmployeeCommandValidator : AbstractValidator<CreateEmployeeCommand>
{
    public CreateEmployeeCommandValidator()
    {
        RuleFor(x => x.Name).NotEmpty().WithMessage("Name is required.");
        RuleFor(x => x.Salary).GreaterThan(0).WithMessage("Salary must be greater than 0.");
        RuleFor(x => x.Department).NotEmpty().WithMessage("Department is required.");
        RuleFor(x => x.Email).EmailAddress().WithMessage("Invalid email address.");
    }
}
``` 

* **Unit Tests**
```C#
using System.Threading.Tasks;
using Microsoft.AspNetCore.Mvc;
using Xunit;

public class EmployeeControllerTests
{
    [Fact]
    public async Task Create_ReturnsBadRequest_WhenModelStateIsInvalid()
    {
        // Arrange
        var commandDispatcher = new FakeCommandDispatcher();
        var controller = new EmployeeController(commandDispatcher);
        controller.ModelState.AddModelError("Email", "Email is required");

        // Act
        var result = await controller.Create(new CreateEmployeeCommand());

        // Assert
        Assert.IsType<BadRequestObjectResult>(result);
    }

    [Fact]
    public async Task Create_ReturnsCreatedAtActionResult_WhenModelStateIsValid()
    {
        // Arrange
        var commandDispatcher = new FakeCommandDispatcher();
        var controller = new EmployeeController(commandDispatcher);
        var command = new CreateEmployeeCommand
        {
            Id = 1,
            Name = "John Doe",
            Salary = 50000,
            Department = "IT",
            Email = "johndoe@example.com"
        };

        // Act
        var result = await controller.Create(command);

        // Assert
        var createdAtActionResult = Assert.IsType<CreatedAtActionResult>(result);
        Assert.Equal(nameof(EmployeeController.Get), createdAtActionResult.ActionName);
        Assert.Equal(1, createdAtActionResult.RouteValues["id"]);
        Assert.Same(command, createdAtActionResult.Value);
    }

    [Fact]
    public async Task Create_CallsCommandDispatcher_WhenModelStateIsValid()
    {
        // Arrange
        var commandDispatcher = new FakeCommandDispatcher();
        var controller = new EmployeeController(commandDispatcher);
        var command = new CreateEmployeeCommand
        {
            Id = 1,
            Name = "John Doe",
            Salary = 50000,
            Department = "IT",
            Email = "johndoe@example.com"
        };

        // Act
        await controller.Create(command);

        // Assert
        Assert.Same(command, commandDispatcher.DispatchedCommand);
    }

    private class FakeCommandDispatcher : ICommandDispatcher
    {
        public ICommand DispatchedCommand { get; private set; }

        public Task DispatchAsync(ICommand command)
        {
            DispatchedCommand = command;
            return Task.CompletedTask;
        }
    }
}
```


| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Should write                | Maybe minor issues. Problems with unit tests and fluent validation |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | No Problems     |
---
<br/><br/>

## 3. Please write a middleware for your API project. For example an error handling middleware
### Answer
> The code block

```C#
using System;
using System.Threading.Tasks;
using Microsoft.AspNetCore.Http;

public class ErrorHandlingMiddleware
{
    private readonly RequestDelegate _next;

    public ErrorHandlingMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    public async Task Invoke(HttpContext context)
    {
        try
        {
            await _next(context);
        }
        catch (Exception ex)
        {
            await HandleExceptionAsync(context, ex);
        }
    }

    private Task HandleExceptionAsync(HttpContext context, Exception ex)
    {
        context.Response.ContentType = "application/json";
        context.Response.StatusCode = (int)HttpStatusCode.InternalServerError;

        var error = new ErrorResponse { Error = ex.Message };
        var json = JsonConvert.SerializeObject(error);

        return context.Response.WriteAsync(json);
    }
}

public class ErrorResponse
{
    public string Error { get; set; }
}
```

```C#
app.UseMiddleware<ErrorHandlingMiddleware>();
```

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Not neccesarily should write |                |
| **L2**    | Should write                | Maybe minor problems   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | No Problems     |
---
<br/><br/>

## 4. Imagine You have a system for managing a book store. Can you please add DB context and write a method for configuring Book model from. And then write a method that queries from database the specified author’s 10 books that have more than 1000 pages, and order them by title.  
### Answer
> The code block

```C#
using System.Collections.Generic;
using System.ComponentModel.DataAnnotations;
using System.ComponentModel.DataAnnotations.Schema;

public class Book
{
    public int Id { get; set; }
    public string Title { get; set; }
    public int AuthorId { get; set; }
    public int Pages { get; set; }
    public Author Author { get; set; }
}

public class Author
{
    public int Id { get; set; }
    public string Name { get; set; }
    public ICollection<Book> Books { get; set; }
}
```

```C#
using Microsoft.EntityFrameworkCore;
using System.Linq;

public class BookStoreDbContext : DbContext
{
    public DbSet<Book> Books { get; set; }
    public DbSet<Author> Authors { get; set; }
    
    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        optionsBuilder.UseSqlServer("Data Source=localhost;Initial Catalog=BookStoreDB;Integrated Security=True");
    }

    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        modelBuilder.Entity<Book>()
            .Property(b => b.Title)
            .IsRequired()
            .HasMaxLength(100);

        modelBuilder.Entity<Book>()
            .Property(b => b.Pages)
            .IsRequired();
    
        modelBuilder.Entity<Book>()
            .HasOne(b => b.Author)
            .WithMany(a => a.Books)
            .HasForeignKey(b => b.AuthorId);

        modelBuilder.Entity<Author>()
            .Property(a => a.Name)
            .IsRequired()
            .HasMaxLength(50);
    }
}
```

```C#
public class BookService
{
    private readonly BookStoreDbContext _dbContext;

    public BookService(BookStoreDbContext dbContext)
    {
        _dbContext = dbContext;
    }

    public List<Book> GetAuthorBooks(string authorName)
    {
        return context.Books
            .Where(b => b.Author.Name == authorName && b.Pages > 1000)
            .OrderBy(b => b.Title)
            .Take(10)
            .ToList();
    }
}
```

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Not neccesarily should write |                |
| **L2**    | Should write                | Maybe minor problems   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | No Problems     |
---
<br/><br/>

## 5. Please write an sql query that gets a collection of books with their prices and titles as well the authors of the book with their name. Price should be more than 100. Sort results by title.
### Answer

```SQL
SELECT b.Title, b.Price, a.Name
FROM Books b
JOIN Authors a
ON b.AuthorId = a.Id
WHERE b.Price > 100
ORDER BY b.Title ASC
```

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Not neccesarily should write |                |
| **L2**    | Should write                | Maybe minor problems   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | No Problems     |
---
<br/><br/>

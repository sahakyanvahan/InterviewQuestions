<h1 align="center">Practical Task</h1>

<br/><br/>

# Note. *Practical task should take no more than 10 minutes. 20 minutes should be considered as red flag.*

## 1. Please write some service that has method for getting a list of employees from some external source.
### Make it asyncronous
### Use dependency injection
### Add unit tests
### Answer

* **Read from external api using `HttpClient`**
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

* **Reads from Database using `Entity Framework`**
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
### Make it asyncronous
### Use dependency injection
### Add unit tests
### Assume you are using CQRS pattern

### Answer
* **The code block with controller and Data Annotation based validation**

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
    private readonly EmployeeDbContext _dbContext;

    public CreateEmployeeCommandHandler(EmployeeDbContext dbContext)
    {
        _dbContext = dbContext;
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

        _dbContext.Employees.Add(employee);
        await dbContext.SaveChangesAsync();
    }
}
```

> * **Same with `Fluent Validation` and `CommandDispatcher`**
```C#
using FluentValidation;
using Microsoft.AspNetCore.Mvc;

public class EmployeeController : ControllerBase
{
    private readonly ICommandDispatcher _commandDispatcher;
    private readonly IValidator<CreateEmployeeCommand> _validator;

    public EmployeeController(ICommandDispatcher commandDispatcher, IValidator<CreateEmployeeCommand> validator)
    {
        _commandDispatcher = commandDispatcher;
        _validator = validator;
    }

    [HttpPost]
    public async Task<IActionResult> Create(CreateEmployeeCommand command)
    {
        var validationResult = await _validator.ValidateAsync(command);

        if (!validationResult.IsValid)
        {
            foreach (var error in validationResult.Errors)
            {
                ModelState.AddModelError(error.PropertyName, error.ErrorMessage);
            }

            return BadRequest(ModelState);
        }

        await _commandDispatcher.DispatchAsync(command);
        return CreatedAtAction(nameof(Get), new { id = command.Id }, command);
    }
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

## 6. Please write an implementation of Command pattern in WPF. We need to bind some action in UI to 
### Answer

```C#
public interface ICommand
{
    bool CanExecute(object parameter);
    void Execute(object parameter);
    event EventHandler CanExecuteChanged;
}

public class MyCommand : ICommand
{
    public bool CanExecute(object parameter)
    {
        // This command can always be executed
        return true;
    }

    public void Execute(object parameter)
    {
        // Perform some action here
        MessageBox.Show("Button clicked!");
    }

    public event EventHandler CanExecuteChanged;
}

<Button Content="Click me!" Command="{Binding MyCommand}" />

public class MyViewModel
{
    public ICommand MyCommand { get; } = new MyCommand();
}
```
> First, let's define a simple ICommand interface:
> Next, we can create a concrete implementation of this interface to represent a command that we want to bind to a control:
> Now, we can use data binding to associate an instance of this command class with a control in our UI. For example, let's say we have a button that we want to bind this command to:
> Here, we've set the Command property of the Button to a binding expression that references an instance of our MyCommand class, which is stored in a property on our view model:
> With this set up, when the user clicks the button, the Execute method of the MyCommand instance will be called, which will in turn show a message box.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Not neccesarily should write |                |
| **L2**    | Should write                | Maybe minor problems   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | No Problems     |
---
<br/><br/>

## 7. Please create an implementation for INotifyPropertyChanged in WPF project and show how to use it
### Answer

```C#
public class MyViewModel : INotifyPropertyChanged
{
    private string _myProperty;

    public string MyProperty
    {
        get { return _myProperty; }
        set
        {
            if (_myProperty != value)
            {
                _myProperty = value;
                OnPropertyChanged(nameof(MyProperty));
            }
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;

    protected virtual void OnPropertyChanged(string propertyName)
    {
        PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }
}

<TextBox Text="{Binding MyProperty}" />
```
> In this example, we have a `MyViewModel` class that implements the `INotifyPropertyChanged` interface. The class has a single property called `MyProperty`, which is backed by a private field `_myProperty`. The `MyProperty` property includes a setter that checks whether the new value is different from the current value. If it is, the property value is updated and the `OnPropertyChanged` method is called to raise the `PropertyChanged` event.

>The `OnPropertyChanged` method is a protected virtual method that raises the `PropertyChanged` event. It takes a single argument, which is the name of the property that has changed. In this example, we're using the `nameof` operator to get the name of the property automatically, but you could also hard-code the property name as a string literal.

>To use this class in a WPF project, you would typically create an instance of `MyViewModel` and set it as the `DataContext` for your user interface elements. Then, you could bind the `MyProperty` property to a control in your UI like this:

>This would bind the `Text` property of a `TextBox` control to the `MyProperty` property of the `MyViewModel` instance, so that changes to the `MyProperty` property would automatically update the text displayed in the `TextBox`.

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

## 6. Write a SQL query to retrieve the top 10 most recently hired employees from the "Employees" table, ordered by hire date in descending order.
### Answer

```SQL
SELECT TOP 10 *
FROM Employees
ORDER BY HireDate DESC
```

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Not neccesarily should write |                |
| **L2**    | Should write                | Maybe minor problems   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | No Problems     |
---
<br/><br/>

## 7. Write a SQL query to retrieve all the products that have a price greater than the average price of all products.
### Answer

```SQL
SELECT *
FROM Products
WHERE Price > (SELECT AVG(Price) FROM Products)
```

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Not neccesarily should write |                |
| **L2**    | Should write                | Maybe minor problems   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | No Problems     |
---
<br/><br/>

## 8. Write a SQL query to retrieve the total number of orders and the total value of all orders for each customer in the "Orders" table.
### Answer

```SQL
SELECT CustomerID,
       COUNT(OrderID) AS TotalOrders,
       SUM(Total) AS TotalValue
FROM Orders
GROUP BY CustomerID
```

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Not neccesarily should write |                |
| **L2**    | Should write                | Maybe minor problems   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | No Problems     |
---
<br/><br/>

## 9. Write a SQL query to retrieve the names and hire dates of all employees who have been with the company for more than 5 years.
### Answer

```SQL
SELECT Name, HireDate
FROM Employees
WHERE DATEDIFF(YEAR, HireDate, GETDATE()) > 5
```

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Not neccesarily should write |                |
| **L2**    | Should write                | Maybe minor problems   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | No Problems     |
---
<br/><br/>
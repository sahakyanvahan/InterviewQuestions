<h1 align="center"> Software design principles and patters </h1>
<br/><br/>

## 1. Are you familiar with any software engineering practices? (SOLID, DRY, KISS, CUPID etc.). Can you please describe them? 
### Answer
> **SOLID**
> >1. Single Responsibility Principle
> >2. Open-Closed Principle
> >3. Liskov Substitution Principle
> >4. Interface Segregation Principle
> >5. Dependency Inversion Principle

> **DRY**
> >DRY stands for "Don't Repeat Yourself." It is a principle of software development that states that code should not have duplication and that there should be one and only one source of truth for any piece of information. The idea is to reduce code redundancy and make it easier to maintain and update code.
 
> **KISS**
> >KISS stands for "Keep It Simple, Stupid." It is a principle of software development that states that code should be simple, easy to understand and easy to maintain. The idea is to avoid complexity and unnecessary features, and to focus on solving the problem at hand in the most straightforward way possible. This principle can be applied to both the design and implementation of software.

> CUPID:
> >1. Composable – “plays well with others”
> >2. Unix – “does one thing well”
> >3. Predictable – “does what you expect”
> >4. Idiomatic – “feels natural”
> >5. Domain-based – “the solution domain models the problem domain in language and structure”

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciptions         | The more the better |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
---
<br/><br/>

## 2. Can you please tell me an example where you used SOLID principles. What was the advantages of using them?
### Answer
> Free answer

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciptions         | Gives resonable example |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
---
<br/><br/>

## 3. Are you familiar with design patterns?  
### Answer
>Design patterns are reusable solutions to common software design problems. They provide a way to structure and organize code in a way that is easy to understand and maintain. Here is a list of some common design patterns, grouped by category:

### **Creational Patterns:**

>**Abstract Factory**: Provides an interface for creating families of related or dependent objects without specifying their concrete classes.

>**Builder**: Separates the construction of a complex object from its representation, allowing the same construction process to create different representations.

>**Factory Method**: Defines an interface for creating an object, but lets subclasses decide which class to instantiate.

>**Prototype**: Creates new objects by copying existing objects, which serves as a prototype.

>**Singleton**: Ensures a class has only one instance, while providing a global access point to this instance.

### **Structural Patterns:**

>**Adapter**: Allows classes with incompatible interfaces to work together by wrapping its own interface around that of an already existing class.

>**Bridge**: Decouples an abstraction from its implementation, allowing the two to vary independently.

>**Composite**: Compose objects into tree structures to represent part-whole hierarchies.

>**Decorator**: Attaches additional responsibilities to an object dynamically.

>**Facade**: Provides a simplified interface to a library, a framework, or any other complex set of classes.

>**Flyweight**: Uses sharing to support large numbers of fine-grained objects efficiently.

>**Proxy**: Provides a surrogate or placeholder for another object to control access to it.

### **Behavioral Patterns:**

>**Chain of Responsibility**: Passes a request sequentially along a dynamic chain of handlers until one of them handles it.

>**Command**: Encapsulates a request as an object, thereby letting you parametrize clients with different requests, queue or log requests, and support undoable operations.
Interpreter: Implements a specialized language by representing its grammar rules as a set of classes.

>**Iterator**: Sequentially access the elements of a collection without exposing its underlying representation.

>**Mediator**: Allows objects to communicate without knowing each other's identities.

>**Memento**: Captures an object's internal state to be able to restore it later.

>**Observer**: Allows a number of observer objects to be notified of changes to another object.

>**State**: Allows an object to alter its behavior when its internal state changes.

>**Strategy**: Defines a family of algorithms, encapsulates each one, and makes them interchangeable.

>**Template Method**: Defines the skeleton of an algorithm as an abstract class, allowing its subclasses to provide concrete behavior.

>**Visitor**: Separates an algorithm from an object structure by moving the hierarchy of methods into one object.

>These are just some of the most common design patterns, there are many more out there. Each pattern serves a specific purpose and can be used in different situations to solve common software design problems. They are not meant to be applied blindly, but rather used as a tool to help guide the design of a software system.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 4. Please describe builder and factory pattern, and what is thee difference between them
>The Builder pattern and the Factory pattern are both creational design patterns used in object-oriented programming to create objects in a controlled and efficient way.

>The main difference between these two patterns lies in their primary use cases and the way they achieve object creation.

>The Builder pattern is used when we want to create complex objects step-by-step, with the ability to customize the creation process along the way. This pattern is useful when we have an object with many optional parameters, or when we need to create a family of related objects that share a common creation process but differ in some of their attributes.

>The Builder pattern typically involves creating a Builder class with methods to set each attribute of the object being created, and a build method that constructs the final object. The client code calls the Builder's methods to set the desired attributes and then calls the build method to get the final product.

>The Factory pattern, on the other hand, is used when we want to create objects of different types based on some criteria, without exposing the creation logic to the client code. This pattern is useful when we need to create objects dynamically, based on user input, configuration settings, or other runtime conditions.

>The Factory pattern typically involves creating a Factory class with a method that takes some input and returns a new instance of a specific class, based on that input. The client code calls the Factory's method to get the desired object, without needing to know how the object is actually created.

>In summary, the Builder pattern is used to create complex objects step-by-step, with customization options, while the Factory pattern is used to create objects of different types based on runtime criteria.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciptions         | Gives resonable example |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
---
<br/><br/>

## 5. What are behavioral design patterns?
>Behavioral design patterns are a set of design patterns that focus on communication and interaction between objects and classes. These patterns describe how objects and classes interact with each other and how they behave in different situations, scenarios, or contexts.

>Behavioral patterns are used to solve common problems in software design related to the interaction and communication of objects and classes. They help to increase the flexibility, extensibility, and reusability of the code by separating the behavior from the implementation.

>There are several behavioral design patterns, including:

> * **Observer pattern:** It defines a one-to-many dependency between objects so that when one object changes its state, all its dependents are notified and updated automatically.

> * **Strategy pattern:** It defines a family of algorithms, encapsulates each one, and makes them interchangeable at runtime.

> * **Command pattern:** It encapsulates a request as an object, thereby allowing for the parameterization of clients with different requests, queue or log requests, and support undoable operations.

> * **Template method pattern:** It defines the skeleton of an algorithm in a base class and allows subclasses to override certain steps of the algorithm without changing its structure.

> * **Iterator pattern:** It provides a way to access the elements of an object sequentially without exposing its underlying representation.

> * **Chain of Responsibility pattern:** It allows a chain of objects to handle a request, where each object in the chain has the ability to either handle the request or pass it on to the next object in the chain.

> * **Interpreter pattern:** It defines a grammar for a language and provides an interpreter to interpret sentences in the language.

>These patterns help to improve the maintainability, scalability, and testability of the software by reducing the coupling and increasing the cohesion between the objects and classes.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciptions         | Gives resonable example |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
---
<br/><br/>

## 6. Can you please describe command pattern. What is the puropse of it? Where it can be used. How it usually implemented?
>The Command pattern is a behavioral design pattern that encapsulates a request as an object, allowing the requesting object to be decoupled from the object that receives and executes the request. The purpose of the Command pattern is to allow clients to request an action without knowing anything about the receiving object or the operation being performed.

>The Command pattern is useful in situations where we need to implement complex undo/redo functionality, support multiple levels of undo, or implement transactional behavior, where a group of operations should be treated as a single unit of work.

>The Command pattern is typically implemented by defining a Command interface that declares an execute method, which encapsulates the action to be performed. Concrete command classes implement the Command interface and encapsulate a specific operation, along with any necessary parameters. The Invoker class maintains a list of Command objects and can execute the commands in the list, typically by calling their execute method.

>The Receiver class is responsible for executing the requested action, typically by invoking methods on itself or other objects. The client creates a Command object and sets its receiver and parameters, and then passes the command object to the Invoker, which adds it to its list of commands.

>When the Invoker is ready to execute the commands, it simply iterates over the list and calls the execute method on each command object. The command object then delegates the request to the appropriate Receiver object, which performs the actual work.

>Here is an example implementation of the Command pattern in C#:

```C#
// Command interface
public interface ICommand
{
    void Execute();
}

// Concrete command classes
public class OpenFileCommand : ICommand
{
    private readonly IFileSystemReceiver _receiver;

    public OpenFileCommand(IFileSystemReceiver receiver)
    {
        _receiver = receiver;
    }

    public void Execute()
    {
        _receiver.OpenFile();
    }
}

public class CloseFileCommand : ICommand
{
    private readonly IFileSystemReceiver _receiver;

    public CloseFileCommand(IFileSystemReceiver receiver)
    {
        _receiver = receiver;
    }

    public void Execute()
    {
        _receiver.CloseFile();
    }
}

// Receiver interface
public interface IFileSystemReceiver
{
    void OpenFile();
    void CloseFile();
}

// Receiver class
public class FileSystemReceiver : IFileSystemReceiver
{
    public void OpenFile()
    {
        Console.WriteLine("File opened");
    }

    public void CloseFile()
    {
        Console.WriteLine("File closed");
    }
}

// Invoker class
public class FileInvoker
{
    private readonly List<ICommand> _commandList = new List<ICommand>();

    public void AddCommand(ICommand command)
    {
        _commandList.Add(command);
    }

    public void ExecuteCommands()
    {
        foreach (var command in _commandList)
        {
            command.Execute();
        }
        _commandList.Clear();
    }
}

// Client code
public class Client
{
    public static void Main(string[] args)
    {
        var receiver = new FileSystemReceiver();
        var openFileCommand = new OpenFileCommand(receiver);
        var closeFileCommand = new CloseFileCommand(receiver);

        var fileInvoker = new FileInvoker();
        fileInvoker.AddCommand(openFileCommand);
        fileInvoker.AddCommand(closeFileCommand);

        fileInvoker.ExecuteCommands();
    }
}
```

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciptions         | Gives resonable example |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
---
<br/><br/>

## 4. Which architectural patterns have you used in your projects? (MVC, MVVM, Layered Architecture, Clean Architecture)  
### Answer
>Free answer

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciptions         | Gives resonable example |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
---
<br/><br/>

## 5. What is Rest API.  
### Answer
>REST (Representational State Transfer) is an architectural style for building web services. A REST API (Application Programming Interface) is a set of rules and conventions for building and interacting with web services that adhere to this architectural style.

>A REST API defines a set of endpoints, or URL paths, that a client can interact with to retrieve and manipulate resources. These endpoints are typically defined according to the specific resource that they represent, and can include standard CRUD (Create, Read, Update, and Delete) operations.

>Each endpoint is typically associated with a specific HTTP verb such as GET, POST, PUT, PATCH, or DELETE. These verbs indicate the type of action that the endpoint should perform, and are used by the client to interact with the API.

>For example, a GET request to the endpoint /users would typically retrieve a list of all users, while a GET request to the endpoint /users/1 would retrieve the user with an ID of 1. A POST request to the endpoint /users would typically create a new user, while a PUT request to the endpoint /users/1 would update the user with an ID of 1.

>REST APIs often return data in the form of JSON or XML, and can be consumed by various clients including web browsers, mobile apps, and servers.

>Benefits of REST API

>RESTful web services are lightweight, highly scalable and maintainable, and are very simple to develop
They are easy to consume, and are often the preferred choice for building web, mobile, and IoT applications.
They are also easy to test, and can be easily integrated with other systems and services.

>The main characteristics of a REST API include:
* **Client-Server architecture**: RESTful APIs follow a client-server architecture, where the client makes requests to the server, and the server responds with the requested data.
* **Stateless**: Each request made to a REST API is self-contained and includes all the information necessary to complete the request. The server does not maintain any client context between requests.
* **Cacheable**: Responses from a REST API can be cached, which can improve performance by reducing the number of requests made to the server.
* **Layered System**: A REST API can be composed of multiple layers, such as the client, the server, and a data store. Each layer can be developed and scaled independently.
* **Use of standard HTTP methods**: RESTful APIs use standard HTTP methods, such as GET, POST, PUT, DELETE, etc. to interact with the resources.
* **Use of URIs**: Resources are identified by URIs, and the API can be accessed using standard HTTP methods and URIs.
* **Return format is JSON or XML**: RESTful API mostly returns the data in JSON or XML format.
* **Platform Independent**: REST API is platform independent, which means any client that understands HTTP can interact with it.
* **Code on demand**: An optional feature of RESTful API is to allow the client to download the code in order to update or improve the functionality.

>In summary, a REST API is a set of rules and conventions for building web services that adhere to the REST architectural style. It defines a set of endpoints that a client can interact with to retrieve and manipulate resources, and is typically associated with standard CRUD operations and HTTP verbs.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Don't know much             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 6. Are you familiar with CQRS pattern  
### Answer
>CQRS (Command-Query Responsibility Segregation) is an architectural pattern that separates the responsibilities of reading and writing data in an application.

>In a CQRS system, the data is split into two separate models: the Command Model, which is responsible for handling write operations, and the Query Model, which is responsible for handling read operations.

>The Command Model is responsible for handling any changes to the data, such as creating new records, updating existing records, or deleting records. The Query Model is responsible for handling any read operations on the data, such as retrieving data from the database.

>The separation of these responsibilities allows for better scalability, performance, and flexibility. Since read and write operations have different requirements and use cases, they can be optimized and scaled independently.

>CQRS pattern can be implemented using different technologies such as Event Sourcing, Domain-Driven Design and Microservices.

>It's important to note that CQRS is not a design pattern for a specific technology or programming language, but a pattern for the architecture of a system.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Don't know                  |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 7.What pattern is used in your project to communicate with the database?
### Answer
>There are several patterns that can be used to communicate with a database in software development. Some of the most commonly used patterns include:

> * **Repository pattern:** This pattern abstracts the data access layer and allows you to define a uniform API for accessing data in your database. This helps to separate the data access logic from the business logic and makes it easier to test and maintain your code.

> * **Unit of Work pattern:** This pattern helps to track changes to objects in memory and ensures that all changes are either committed or rolled back in a single transaction when communicating with a database. This can help to improve the reliability and performance of your database interactions.

> * **Data Mapper pattern:** This pattern separates the object mapping from the database access logic, making it easier to manage changes to the database schema and objects used in the application.

> * **Active Record pattern:** This pattern is an object-oriented approach to database access, where each object represents a database record and provides methods for manipulating the data. This can simplify database access and make it easier to work with database records in your application.

>The choice of pattern will depend on the specific requirements of your application, and there may be other patterns that are better suited to your use case. It's also worth noting that many modern web frameworks provide built-in support for database communication, and you may not need to implement these patterns manually in your code.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Don't know                  |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 7.What is microservice architecture. What are the core advantages of using microservices architecture
### Answer
>Microservice architecture is a software design pattern where a large application is decomposed into a collection of smaller, independent services that communicate with each other through well-defined APIs. The goal of this architecture is to improve scalability, maintainability, and resilience by breaking down a monolithic application into smaller, loosely coupled components that can evolve and be deployed independently.

>Each microservice in a microservice architecture is responsible for a specific business capability and operates as a separate process, with its own database and independent deployment cycle. This allows for faster development and deployment, as well as easier scaling of individual components.

>However, this architecture also comes with certain challenges, such as increased operational complexity, the need for effective communication between services, and the need for robust service discovery and routing mechanisms.

>Overall, microservice architecture is well-suited for complex, large-scale applications where the traditional monolithic architecture can become difficult to manage and evolve over time.

> ### **Pros**
> * **Scalability**: Microservices allow for individual services to be scaled independently, allowing for greater flexibility in managing the load and performance of the system.
> * **Resilience**: By breaking down the system into smaller, independent services, the impact of a failure in one service is limited to that service, rather than affecting the entire system.
> * **Flexibility**: Microservices can be developed, deployed, and updated independently, allowing for faster release cycles and more flexible innovation.
> * **Technology Heterogeneity**: Microservices can be built using different technologies that are best suited to the specific service, rather than being limited to a single technology stack for the entire system.
> * **Improved fault isolation**: The smaller, isolated components of microservices make it easier to identify and fix problems in the system.
> * **Cost Savings**: By breaking down the system into smaller, modular components, it becomes easier to manage the costs of development, testing, and deployment.
> * **Improved DevOps**: Microservices promote DevOps best practices such as continuous integration, delivery, and deployment, which results in faster and more reliable software delivery.

> ### **Cons**
> * **Complexity:** With many independent services, the overall system can become more complex to manage, monitor, and test.
> * **Communication overhead:** Microservices must communicate with each other, and this communication can add latency and increase the risk of failure, which requires careful design and testing to mitigate.
> * **Integration issues:** Integration between services can be more difficult and time-consuming, requiring more effort to ensure data consistency and ensure that services are correctly communicating with each other.
> * **Increased operational overhead:** With many services to manage, monitoring and maintaining the system can be more challenging, requiring a larger and more specialized operations team.
> * **Increased testing overhead:** Testing a microservice-based system can be more complex, requiring more testing effort to ensure that services are working correctly together.
> 
>Overall, the microservices architecture allows for greater agility, scalability, and resilience, making it a popular choice for modern, complex software systems.



| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 8.What is DDD. What are the main concepts of it?
### Answer
>DDD (Domain-Driven Design) is a software design approach that focuses on defining and solving business problems and processes through software. It is a method for creating complex and scalable software systems that are aligned with the needs of the business. /
>The main concepts of DDD are:
>* **Bounded Context:** This defines the scope of a domain model and provides the context for its components.
>* **Domain Model:** A representation of the business concepts and rules in the problem space.
>* **Entity:** A unique and identifiable object in the problem space with its own lifecycle.
>* **Value Object:** An object that represents a simple value in the problem space, such as a date or a monetary amount, and does not have an identity of its own.
>* **Aggregate:** A group of objects that are treated as a single unit and have a single root entity.
>* **Repository:** A mechanism for retrieving and storing domain objects.
>* **Services:** Operations that do not naturally fit within an Entity or Value Object, but still represent a business capability.
>* **Ubiquitous Language:** A shared language between the development team and the business stakeholders, used to ensure that the software design accurately reflects the business needs.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 9. What is Liskov substitution principle?
### Answer
>The Liskov Substitution Principle (LSP) is a principle in object-oriented programming that states that objects of a superclass should be able to be replaced with objects of a subclass without affecting the correctness of the program. In simpler terms, it means that if a program is written to work with a certain type of object, it should be able to work with any subtype of that object without any modification.

>For example, if you have a Vehicle class, and you create a Car class that inherits from the Vehicle class, the Liskov Substitution Principle states that any code that is written to work with a Vehicle object should be able to work with a Car object without any modification, because a Car is a type of Vehicle.

>The Liskov Substitution Principle is related to the concept of polymorphism, which allows objects of different classes to be used interchangeably, as long as they implement a common interface. To follow the LSP, the derived classes should be substitutable for their base classes, and it should be able to use any derived class in place of its base class without altering the desirable properties of the program.

>The LSP is important to make sure that the code is easy to understand, maintain, and extend. It helps to reduce the number of dependencies between different parts of the code, making the code more robust and less prone to errors.

>It's important to note that the LSP is not a hard rule and it's not always easy or practical to follow it strictly. Sometimes, it's necessary to break the LSP in order to achieve other goals, such as performance or security. But it should be done with care, and always in a way that's easy to understand, maintain, and extend.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciptions         | Gives resonable example |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
---
<br/><br/>

## 10. What is validation. Where and why it is used? 
### Answer
>Validation is the process of checking that data entered into a system conforms to a set of rules or constraints. It is used to ensure that the data is accurate, complete, and in the correct format.

>Validation is typically used in forms, input fields and APIs to validate input data.

>Validation is important because it helps to ensure the integrity of data stored in a system, and can prevent errors and inconsistencies from occurring. It can also help to protect the system from malicious input, such as SQL injection attacks.

>Validation can be performed on both the client-side and server-side of an application. Client-side validation is performed by JavaScript or other client-side scripting languages, and can provide immediate feedback to the user about any errors in the input data. Server-side validation is performed by the application after the data has been submitted and can provide a more secure form of validation as it cannot be bypassed by malicious users.

>Validation can be performed in many ways, such as using regular expressions, comparing input to a predefined list of accepted values, or using a validation library or framework. It is mostly used in web development, in forms and APIs to ensure the data entered by the user or client is correct and in the correct format before it is processed by the server. It also helps in preventing data loss and data corruption, and also helps in maintaining the data quality and consistency.

>.NET developers have a variety of tools and techniques available for validation in their applications. Some popular ones include:

>Data Annotation Attributes: These are attributes that can be applied to properties of a model class to specify validation rules. Examples include `[Required]`, `[Range]`, and `[RegularExpression]`. These attributes can be used with the `ModelState.IsValid` property in ASP.NET Core MVC to perform validation on the server-side.

> **Model Validation**: Model validation is a technique that allows developers to define validation rules on a model class. These rules can be specified using Data Annotation Attributes or by creating a custom validation attribute.

> **Fluent Validation**: FluentValidation is an open-source library that allows developers to define validation rules using a fluent interface. It provides a simple and flexible way to define validation rules and is well-suited to complex validation scenarios.

> **ASP.NET Core Tag Helpers**: These are built-in tag helpers that can be used to perform validation on the client-side. These tag helpers can be used to display error messages and validation summaries, and can also be used to disable form elements based on the validation state of the form.

> **Client-side JavaScript Validation**: This is a technique that allows developers to perform validation on the client-side using JavaScript or other client-side scripting languages. This can provide immediate feedback to the user about any errors in the input data.

> **Regex**: Regular expressions are a powerful tool for validating input data. .NET provides a built-in class Regex for working with regular expressions.

>These are just a few examples of the tools and techniques available for validation in .NET, depending on the specific needs of the application, developers can choose the best tool that fits the requirement.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 11. What is caching. Have you used it? What tools you have used? 
### Answer
>Caching is a technique of storing frequently accessed data in a temporary storage area, called a cache, to speed up future access to the data. Caching is commonly used in computer science and software engineering to improve the performance of systems by reducing the need to access slower storage media or retrieve data over a network.
Microsoft's in-memory caching framework, ASP.NET Core Memory Cache: This is a built-in caching mechanism provided by the ASP.NET Core framework that allows developers to cache data in memory.

* **Microsoft's distributed caching framework, ASP.NET Core Distributed Cache**: This is a caching mechanism provided by the ASP.NET Core framework that allows developers to cache data across multiple servers in a distributed environment.

* **Redis**: An open-source, in-memory data store that supports a wide range of data structures and can be used as a caching tool.

* **Memcached**: An open-source, in-memory key-value store that is often used as a caching tool.

* **NCache**: A commercial, in-memory distributed caching solution for .NET developers. It supports various data structures like dictionaries, lists, etc.

* **StackExchange.Redis** : it is a high-performance general-purpose redis client for .NET languages.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Don't know much             |                 |
| **L2**    | Basic   Knowledge           |                 |
| **L3**    | Strong in Depth Knowledge   |                 |
---
<br/><br/>

## 12. Describe please step by step the process of sending a request to server and getting a response 
### Answer
>When a client, such as a web browser, wants to send a request to a server over HTTPS, the following steps take place:

>The client initiates a secure SSL/TLS connection with the server by sending a request to establish a secure session. This request includes the client's SSL/TLS supported versions and the client's SSL/TLS supported ciphers.

>The server responds with its own SSL/TLS supported versions and ciphers, along with its SSL/TLS certificate, which includes the server's public key. The client verifies the authenticity of the server certificate by checking it against a trusted certificate authority (CA) or a locally stored list of trusted CAs.

>Once the SSL/TLS session is established, the client and the server use the agreed-upon cipher to exchange a symmetric key that will be used for encrypting all further communication.

>The client sends the request to the server using the HTTP protocol. In this case, the request is encapsulated in an SSL/TLS encrypted message. The request includes the URL, the HTTP method (e.g., GET, POST), any headers and the data that needs to be sent to the server.

>The server receives the request, decrypts the message using the symmetric key, and processes the request. The server may look up data in a database, perform calculations, or generate dynamic content based on the request.

>The server generates the response, encrypts it using the symmetric key, and sends it back to the client. The response includes the HTTP status code (e.g., 200 for success, 404 for not found), the response body (i.e., the data returned by the server), and any headers that are required.

>The client receives the response, decrypts the message using the symmetric key, and processes the response. This may involve displaying the response data in a web page, or using the data to update the state of the application.

>The SSL/TLS session is closed and the communication between the client and the server is terminated.

# .NET SERVER PART
>ASP.NET is a web application framework for building web applications using the .NET framework. Here is a general overview of how ASP.NET handles requests and creates responses:

>A client, such as a web browser, sends a request to an ASP.NET web server using the HTTP protocol. The request includes details such as the URL, the HTTP method (e.g., GET, POST), and any data that needs to be sent to the server.

>The request is received by the web server, which then forwards the request to the ASP.NET runtime. The ASP.NET runtime is responsible for processing requests and creating responses.

>The ASP.NET runtime checks the URL of the request against the routing configuration of the application. The routing configuration maps URLs to specific controllers or actions.

>If the URL matches a configured route, the ASP.NET runtime creates an instance of the corresponding controller and calls the appropriate action method. The action method can perform various tasks, such as looking up data in a database, performing calculations, or generating dynamic content.

>Once the action method has finished executing, the controller creates a view model, which is a model that contains the data that needs to be rendered by the view.

>The controller then selects the appropriate view to render the view model. The view is a template that defines the layout and structure of the HTML that will be sent back to the client.

>The view is then rendered by the view engine, which uses the view model data to create the final HTML response. The response is then sent back to the client by the web server.

>The client receives the response, processes it, and displays it in the browser.

>Note that this process can be more complex in real-world scenarios, for example:

>The server might use caching to avoid recomputing the same response for multiple requests;
The communication can be encrypted using https instead of http
The request and response can contain many more headers, like cookies, auth token, content-type, etc
The server can forward the request to another server, this process can happen multiple times before the final response is sent to the client.
Also, ASP.NET Core is the latest version of ASP.NET, which is a redesign of the original ASP.NET and it has some differences in the way it handles requests and creates responses compared to the older versions of ASP.NET

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciptions         | The more the better |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑   |
---
<br/><br/>

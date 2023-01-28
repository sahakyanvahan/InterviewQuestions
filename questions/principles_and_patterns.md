<h1 align="center"> Software design principles and patters </h1>
<br/><br/>

## 1. Are you familiar with any software engineering practices? (SOLID, DRY, KISS, CUPID etc.). Can you please describe them? 
### Answer

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>

## 2. Can you please tell me an example where you used SOLID principles. What was the advantage of using it.
### Answer
>1. Single Responsibility Principle
>2. Open-Closed Principle
>3. Liskov Substitution Principle
>4. Interface Segregation Principle
>5. Dependency Inversion Principle

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>
## 3. Are you familiar with design patterns?  
### Answer
>Design patterns are reusable solutions to common software design problems. They provide a way to structure and organize code in a way that is easy to understand and maintain. Here is a list of some common design patterns, grouped by category:

### Creational Patterns:

**Abstract Factory**: Provides an interface for creating families of related or dependent objects without specifying their concrete classes.
**Builder**: Separates the construction of a complex object from its representation, allowing the same construction process to create different representations.
**Factory Method**: Defines an interface for creating an object, but lets subclasses decide which class to instantiate.
**Prototype**: Creates new objects by copying existing objects, which serves as a prototype.
**Singleton**: Ensures a class has only one instance, while providing a global access point to this instance.

### Structural Patterns:

**Adapter**: Allows classes with incompatible interfaces to work together by wrapping its own interface around that of an already existing class.
**Bridge**: Decouples an abstraction from its implementation, allowing the two to vary independently.
**Composite**: Compose objects into tree structures to represent part-whole hierarchies.
**Decorator**: Attaches additional responsibilities to an object dynamically.
**Facade**: Provides a simplified interface to a library, a framework, or any other complex set of classes.
**Flyweight**: Uses sharing to support large numbers of fine-grained objects efficiently.
**Proxy**: Provides a surrogate or placeholder for another object to control access to it.

### Behavioral Patterns:

**Chain of Responsibility**: Passes a request sequentially along a dynamic chain of handlers until one of them handles it.
**Command**: Encapsulates a request as an object, thereby letting you parametrize clients with different requests, queue or log requests, and support undoable operations.
Interpreter: Implements a specialized language by representing its grammar rules as a set of classes.
**Iterator**: Sequentially access the elements of a collection without exposing its underlying representation.
**Mediator**: Allows objects to communicate without knowing each other's identities.
**Memento**: Captures an object's internal state to be able to restore it later.
**Observer**: Allows a number of observer objects to be notified of changes to another object.
**State**: Allows an object to alter its behavior when its internal state changes.
**Strategy**: Defines a family of algorithms, encapsulates each one, and makes them interchangeable.
**Template Method**: Defines the skeleton of an algorithm as an abstract class, allowing its subclasses to provide concrete behavior.
**Visitor**: Separates an algorithm from an object structure by moving the hierarchy of methods into one object.

>These are just some of the most common design patterns, there are many more out there. Each pattern serves a specific purpose and can be used in different situations to solve common software design problems. They are not meant to be applied blindly, but rather used as a tool to help guide the design of a software system.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>

## 4. Which architectural patterns have you used in your projects? (MVC, MVVM, Layered Architecture, Clean Architecture)  
### Answer

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
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

>In summary, a REST API is a set of rules and conventions for building web services that adhere to the REST architectural style. It defines a set of endpoints that a client can interact with to retrieve and manipulate resources, and is typically associated with standard CRUD operations and HTTP verbs.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>

## 5. Are you familiar with CQRS pattern  
### Answer

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>

## 6. What is validation. Where and why it is used? 
### Answer
>Validation is the process of checking that data entered into a system conforms to a set of rules or constraints. It is used to ensure that the data is accurate, complete, and in the correct format.
Validation is typically used in forms, input fields and APIs to validate input data.
Validation is important because it helps to ensure the integrity of data stored in a system, and can prevent errors and inconsistencies from occurring. It can also help to protect the system from malicious input, such as SQL injection attacks.
Validation can be performed on both the client-side and server-side of an application. Client-side validation is performed by JavaScript or other client-side scripting languages, and can provide immediate feedback to the user about any errors in the input data. Server-side validation is performed by the application after the data has been submitted and can provide a more secure form of validation as it cannot be bypassed by malicious users.

>Validation can be performed in many ways, such as using regular expressions, comparing input to a predefined list of accepted values, or using a validation library or framework.
It is mostly used in web development, in forms and APIs to ensure the data entered by the user or client is correct and in the correct format before it is processed by the server.
It also helps in preventing data loss and data corruption, and also helps in maintaining the data quality and consistency.
>.NET developers have a variety of tools and techniques available for validation in their applications. Some popular ones include:

Data Annotation Attributes: These are attributes that can be applied to properties of a model class to specify validation rules. Examples include [Required], [Range], and [RegularExpression]. These attributes can be used with the ModelState.IsValid property in ASP.NET Core MVC to perform validation on the server-side.

Model Validation: Model validation is a technique that allows developers to define validation rules on a model class. These rules can be specified using Data Annotation Attributes or by creating a custom validation attribute.

Fluent Validation: FluentValidation is an open-source library that allows developers to define validation rules using a fluent interface. It provides a simple and flexible way to define validation rules and is well-suited to complex validation scenarios.

ASP.NET Core Tag Helpers: These are built-in tag helpers that can be used to perform validation on the client-side. These tag helpers can be used to display error messages and validation summaries, and can also be used to disable form elements based on the validation state of the form.

Client-side JavaScript Validation: This is a technique that allows developers to perform validation on the client-side using JavaScript or other client-side scripting languages. This can provide immediate feedback to the user about any errors in the input data.

Regex: Regular expressions are a powerful tool for validating input data. .NET provides a built-in class Regex for working with regular expressions.

These are just a few examples of the tools and techniques available for validation in .NET, depending on the specific needs of the application, developers can choose the best tool that fits the requirement.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>

## 7. What is caching. Have you used it? What tools you have used? 
### Answer
>Caching is a technique of storing frequently accessed data in a temporary storage area, called a cache, to speed up future access to the data. Caching is commonly used in computer science and software engineering to improve the performance of systems by reducing the need to access slower storage media or retrieve data over a network.
Microsoft's in-memory caching framework, ASP.NET Core Memory Cache: This is a built-in caching mechanism provided by the ASP.NET Core framework that allows developers to cache data in memory.

>>Microsoft's distributed caching framework, ASP.NET Core Distributed Cache: This is a caching mechanism provided by the ASP.NET Core framework that allows developers to cache data across multiple servers in a distributed environment.

>>Redis: An open-source, in-memory data store that supports a wide range of data structures and can be used as a caching tool.

>>Memcached: An open-source, in-memory key-value store that is often used as a caching tool.

>>NCache: A commercial, in-memory distributed caching solution for .NET developers. It supports various data structures like dictionaries, lists, etc.

>>StackExchange.Redis : it is a high-performance general-purpose redis client for .NET languages.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>

## 8. Describe please step by step the process of sending a request to server and getting a response 
### Answer
>When a client, such as a web browser, wants to send a request to a server over HTTPS, the following steps take place:

The client initiates a secure SSL/TLS connection with the server by sending a request to establish a secure session. This request includes the client's SSL/TLS supported versions and the client's SSL/TLS supported ciphers.

The server responds with its own SSL/TLS supported versions and ciphers, along with its SSL/TLS certificate, which includes the server's public key. The client verifies the authenticity of the server certificate by checking it against a trusted certificate authority (CA) or a locally stored list of trusted CAs.

Once the SSL/TLS session is established, the client and the server use the agreed-upon cipher to exchange a symmetric key that will be used for encrypting all further communication.

The client sends the request to the server using the HTTP protocol. In this case, the request is encapsulated in an SSL/TLS encrypted message. The request includes the URL, the HTTP method (e.g., GET, POST), any headers and the data that needs to be sent to the server.

The server receives the request, decrypts the message using the symmetric key, and processes the request. The server may look up data in a database, perform calculations, or generate dynamic content based on the request.

The server generates the response, encrypts it using the symmetric key, and sends it back to the client. The response includes the HTTP status code (e.g., 200 for success, 404 for not found), the response body (i.e., the data returned by the server), and any headers that are required.

The client receives the response, decrypts the message using the symmetric key, and processes the response. This may involve displaying the response data in a web page, or using the data to update the state of the application.

The SSL/TLS session is closed and the communication between the client and the server is terminated.

# .NET SERVER PART
>ASP.NET is a web application framework for building web applications using the .NET framework. Here is a general overview of how ASP.NET handles requests and creates responses:

A client, such as a web browser, sends a request to an ASP.NET web server using the HTTP protocol. The request includes details such as the URL, the HTTP method (e.g., GET, POST), and any data that needs to be sent to the server.

The request is received by the web server, which then forwards the request to the ASP.NET runtime. The ASP.NET runtime is responsible for processing requests and creating responses.

The ASP.NET runtime checks the URL of the request against the routing configuration of the application. The routing configuration maps URLs to specific controllers or actions.

If the URL matches a configured route, the ASP.NET runtime creates an instance of the corresponding controller and calls the appropriate action method. The action method can perform various tasks, such as looking up data in a database, performing calculations, or generating dynamic content.

Once the action method has finished executing, the controller creates a view model, which is a model that contains the data that needs to be rendered by the view.

The controller then selects the appropriate view to render the view model. The view is a template that defines the layout and structure of the HTML that will be sent back to the client.

The view is then rendered by the view engine, which uses the view model data to create the final HTML response. The response is then sent back to the client by the web server.

The client receives the response, processes it, and displays it in the browser.

Note that this process can be more complex in real-world scenarios, for example:

The server might use caching to avoid recomputing the same response for multiple requests;
The communication can be encrypted using https instead of http
The request and response can contain many more headers, like cookies, auth token, content-type, etc
The server can forward the request to another server, this process can happen multiple times before the final response is sent to the client.
Also, ASP.NET Core is the latest version of ASP.NET, which is a redesign of the original ASP.NET and it has some differences in the way it handles requests and creates responses compared to the older versions of ASP.NET


| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>

## 8. What is Liskov substitution principle?
### Answer

>The Liskov Substitution Principle (LSP) is a principle in object-oriented programming that states that objects of a superclass should be able to be replaced with objects of a subclass without affecting the correctness of the program. In simpler terms, it means that if a program is written to work with a certain type of object, it should be able to work with any subtype of that object without any modification.

>For example, if you have a Vehicle class, and you create a Car class that inherits from the Vehicle class, the Liskov Substitution Principle states that any code that is written to work with a Vehicle object should be able to work with a Car object without any modification, because a Car is a type of Vehicle.

>The Liskov Substitution Principle is related to the concept of polymorphism, which allows objects of different classes to be used interchangeably, as long as they implement a common interface. To follow the LSP, the derived classes should be substitutable for their base classes, and it should be able to use any derived class in place of its base class without altering the desirable properties of the program.

>The LSP is important to make sure that the code is easy to understand, maintain, and extend. It helps to reduce the number of dependencies between different parts of the code, making the code more robust and less prone to errors.

>It's important to note that the LSP is not a hard rule and it's not always easy or practical to follow it strictly. Sometimes, it's necessary to break the LSP in order to achieve other goals, such as performance or security. But it should be done with care, and always in a way that's easy to understand, maintain, and extend.


| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>
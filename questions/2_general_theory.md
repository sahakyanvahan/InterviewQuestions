<h1 align="center"> General Programming Theory</h1>

<br/><br/>

## 1. What is OOP?
### Answer
>Object-oriented programming (OOP) is a programming paradigm that is based on the concept of "objects", which are instances of classes that contain both data and behavior. OOP is a way of organizing and structuring code that is designed to make it more reusable, modular, and maintainable.

>Some of the key concepts in OOP include:

* **Classes**: These are templates or blueprints for creating objects. A class defines the properties (data) and methods (behavior) of an object.

* **Objects**: These are instances of classes that contain both data and behavior. An object is an individual instance of a class and it has its own set of properties and methods.

* **Inheritance**: This is a mechanism that allows one class to inherit the properties and methods of another class, allowing for code reuse and a more hierarchical organization of code.

* **Polymorphism**: This is the ability for objects of different classes to be used interchangeably, as long as they implement a common interface.

* **Encapsulation**: This is the practice of keeping the internal state and behavior of an object hidden from the outside world, and only exposing a public interface that can be used to interact with the object.

>OOP is widely used in modern programming languages like Java, C#, Python, and many more. It's important to note that OOP is just one of the many programming paradigms and it's not the only way to solve a problem, other paradigms like functional programming and procedural programming also can be used to solve problems.

---
<br/><br/>

## 2. What is polymorphism?
### Answer

>Polymorphism is a fundamental concept in object-oriented programming (OOP) that refers to the ability of objects of different classes to be used interchangeably, as long as they implement a common interface. Polymorphism allows you to write code that can work with multiple types of objects in a consistent and predictable way, without having to know or care about the specific type of the object at runtime.

>There are two main types of polymorphism:

* **Compile-time polymorphism** (also known as static polymorphism or overloading): This is achieved through method overloading, where multiple methods with the same name but different signatures can be defined in the same class or derived classes.

* **Run-time polymorphism** (also known as dynamic polymorphism or overriding): This is achieved through method overriding, where a method in a derived class has the same name and signature as a method in the base class, and can be used to override the behavior of the base class method.

>An example of polymorphism is a shape class hierarchy where a `Shape` class has a `Draw()` method, and derived classes like `Circle`, `Square`, and `Triangle` have their own implementation of the `Draw()` method, and using polymorphism, you can call the `Draw()` method on a Shape reference that could be a Circle, Square or Triangle without knowing the specific type of the object at runtime.

---
<br/><br/>

## 3. What is encapsulaltion?
### Answer
>Encapsulation is a fundamental concept in object-oriented programming (OOP) that refers to the practice of keeping the internal state and behavior of an object hidden from the outside world, and only exposing a public interface that can be used to interact with the object. The main goal of encapsulation is to protect the integrity of the object's internal state and to hide the implementation details of the object from the outside world.

>Encapsulation is typically achieved through the use of access modifiers (such as public, private, protected, etc.) that control the visibility of the object's properties and methods. For example, a class can have a private field that represents the internal state of the object, and a public method that allows other objects to access or modify the internal state of the object in a controlled and predictable way.

>Encapsulation provides several benefits such as:

* It allows the developer to change the implementation of an object without affecting the code that uses the object.
* It helps to isolate the effects of changes, making the system more robust and less prone to errors.
* It promotes the use of a clear and consistent interface for interacting with the object, making the code more readable and maintainable.
* It allows the developer to implement security mechanisms, such as access control, to prevent unauthorized access to the object's internal state and behavior.

>It is important to note that encapsulation is not about hiding information, it is about controlling the access to the information and keeping the object's internal state and behavior consistent and predictable.

---
<br/><br/>

## 4. What is inheritance
### Answer
>Inheritance is a fundamental concept in object-oriented programming (OOP) that allows one class to inherit the properties and methods of another class, allowing for code reuse and a more hierarchical organization of code. The class that inherits from another class is called a derived class, and the class from which it inherits is called a base class.

>The main advantage of inheritance is that it allows a developer to create new classes that are based on existing classes, without having to rewrite the same code. The derived class inherits all of the properties and methods of the base class, and can also add new properties and methods or override existing ones.

>For example, let's consider that you have a `Vehicle` class that has properties such as `Make`, `Model`, `Year` and methods such as `Start()`, `Stop()`, `Accelerate()` and you want to create a `Car` class that inherits from the `Vehicle` class, the `Car` class will have all properties and methods of the `Vehicle` class plus the additional properties and methods that are specific to cars such as `NumberOfDoors`, `NumberOfSeats`, etc.

>Inheritance also allows for a more hierarchical organization of code, where a base class represents a general concept and derived classes represent more specific concepts. This makes it easier to understand and maintain the code, as the developer can easily see the relationship between classes and understand how the code is organized.

>Inheritance is one of the fundamental concepts of OOP, and it is supported by most modern programming languages, including Java, C#, Python, and many more. It's important to note that Inheritance is just one way of achieving code reuse, other ways of code reuse are composition and interfaces.

---
<br/><br/>

## 5. What is technical debt?
### *Answer*
>Technical debt refers to the cost of maintaining and enhancing software over time. It is a metaphor used to describe the trade-off between investing in short-term workarounds, quick-fixes, and other shortcuts to meet immediate needs, and investing in more robust, long-term solutions that may require more time and resources up front.

>The idea is that, just as financial debt incurs interest, technical debt incurs `interest` in the form of extra effort that must be expended in the future to maintain or enhance the software. This extra effort can come in the form of additional development work, increased testing, or higher maintenance costs.

>The goal is to minimize technical debt by designing and building software in a maintainable and scalable way, so that it can be easily updated and extended as business needs change. This is important because as the technical debt increases, it can become harder and more expensive to make changes to the software, which can slow down development and impact the business.

---
<br/><br/>

## 6. What is SDLC?
### *Answer*
>The software development life cycle (SDLC) is a process used by software engineers to plan, design, develop, test, and maintain software. The SDLC typically includes the following stages:

* **Requirements gathering and analysis**: This stage involves identifying the needs and goals of the software and determining the requirements that the software must meet.
* **Design**: This stage involves creating a plan for how the software will be built and outlining the overall architecture of the system.
* **Implementation or coding**: This stage involves writing the code for the software and bringing the design to life.
* **Testing**: This stage involves verifying that the software works correctly and meets the requirements defined in the previous stages.
* **Deployment**: This stage involves installing the software on the target system or making it available for use by end-users.
* **Maintenance**: This stage involves monitoring the software after it is deployed and making any necessary updates or improvements.

>Different methodologies like Waterfall, Agile, Scrum, V-model etc are used to follow the above stages but it's not necessary that every SDLC model follows all the stages, it may vary as per organization and project requirement.

---
<br/><br/>

## 7. What are code metrics?
### *Answer*
>Code metrics are measurements used to evaluate the quality and maintainability of software. Some common code metrics include:

* **Lines of code (LOC)**: This metric measures the total number of lines of code in a software program.
* **Cyclomatic complexity**: This metric measures the number of linearly independent paths through a program's source code. It is used to identify complex and hard-to-maintain code.
* **Maintainability index**: This metric is calculated based on several other metrics, such as LOC, cyclomatic complexity, and number of comments, and is used to evaluate the overall maintainability of a software program.
* **Comment density**: This metric measures the number of comments in a software program relative to the number of lines of code.
* **Code coverage**: This metric measures the proportion of a program's code that is executed during testing.
* **Bug density**: This metric measures the number of bugs found per unit of code.
* **Code duplication**: This metric measures the amount of duplicate code in a software program.

> These metrics can provide valuable insight into the quality and maintainability of a software program and can help software engineers identify areas of the code that may need improvement.

>There are several tools that can be used to measure code metrics in C#, including:

* **Visual Studio Code Metrics PowerTool**: This is a built-in tool in Visual Studio that can be used to measure code metrics such as lines of code, cyclomatic complexity, and number of types and members.
* **NDepend**: This is a third-party tool that provides a wide range of code metrics and analysis features, including code coverage, code rule enforcement, and code quality visualization.
* **SonarQube**: This is an open-source platform for code quality management that supports C# and other languages. It provides a wide range of code metrics and can be integrated with various build tools and IDEs.
* **StyleCop**: This is a code analysis tool that checks C# code for conformance to a set of style and consistency rules.
* **Metrics.NET**: This is an open-source tool that can be used to measure code metrics such as cyclomatic complexity, lines of code, and number of methods in C# projects.
* **CodeCracker**: This is an open-source tool that analyses code and finds issues, such as performance, security, style, and maintainability.
> 

---
<br/><br/>

## 8. What is validation. Where and why it is used? 
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

---
<br/><br/>

## 9. What is caching. Have you used it? What tools you have used? 
### Answer
>Caching is a technique of storing frequently accessed data in a temporary storage area, called a cache, to speed up future access to the data. Caching is commonly used in computer science and software engineering to improve the performance of systems by reducing the need to access slower storage media or retrieve data over a network.
Microsoft's in-memory caching framework, ASP.NET Core Memory Cache: This is a built-in caching mechanism provided by the ASP.NET Core framework that allows developers to cache data in memory.

* **Microsoft's distributed caching framework, ASP.NET Core Distributed Cache**: This is a caching mechanism provided by the ASP.NET Core framework that allows developers to cache data across multiple servers in a distributed environment.

* **Redis**: An open-source, in-memory data store that supports a wide range of data structures and can be used as a caching tool.

* **Memcached**: An open-source, in-memory key-value store that is often used as a caching tool.

* **NCache**: A commercial, in-memory distributed caching solution for .NET developers. It supports various data structures like dictionaries, lists, etc.

* **StackExchange.Redis** : it is a high-performance general-purpose redis client for .NET languages.

---
<br/><br/>

## 10. Describe please step by step the process of sending a request to server and getting a response 
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

---
<br/><br/>

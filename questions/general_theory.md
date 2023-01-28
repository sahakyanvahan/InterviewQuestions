<h1 align="center"> General Theory</h1>

<br/><br/>

## 1. What is OOP
### Answer
>Object-oriented programming (OOP) is a programming paradigm that is based on the concept of "objects", which are instances of classes that contain both data and behavior. OOP is a way of organizing and structuring code that is designed to make it more reusable, modular, and maintainable.

>Some of the key concepts in OOP include:

>Classes: These are templates or blueprints for creating objects. A class defines the properties (data) and methods (behavior) of an object.

>Objects: These are instances of classes that contain both data and behavior. An object is an individual instance of a class and it has its own set of properties and methods.

>Inheritance: This is a mechanism that allows one class to inherit the properties and methods of another class, allowing for code reuse and a more hierarchical organization of code.

>Polymorphism: This is the ability for objects of different classes to be used interchangeably, as long as they implement a common interface.

>Encapsulation: This is the practice of keeping the internal state and behavior of an object hidden from the outside world, and only exposing a public interface that can be used to interact with the object.

>OOP is widely used in modern programming languages like Java, C#, Python, and many more. It's important to note that OOP is just one of the many programming paradigms and it's not the only way to solve a problem, other paradigms like functional programming and procedural programming also can be used to solve problems.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>

## 2. What is polymorphism
### Answer

>Polymorphism is a fundamental concept in object-oriented programming (OOP) that refers to the ability of objects of different classes to be used interchangeably, as long as they implement a common interface. Polymorphism allows you to write code that can work with multiple types of objects in a consistent and predictable way, without having to know or care about the specific type of the object at runtime.

>There are two main types of polymorphism:

>Compile-time polymorphism (also known as static polymorphism or overloading): This is achieved through method overloading, where multiple methods with the same name but different signatures can be defined in the same class or derived classes.

>Run-time polymorphism (also known as dynamic polymorphism or overriding): This is achieved through method overriding, where a method in a derived class has the same name and signature as a method in the base class, and can be used to override the behavior of the base class method.

>An example of polymorphism is a shape class hierarchy where a Shape class has a Draw() method, and derived classes like Circle, Square, and Triangle have their own implementation of the Draw() method, and using polymorphism, you can call the draw method on a Shape reference that could be a Circle, Square or Triangle without knowing the specific type of the object at runtime.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>

## 3. What is encapsulaltion
### Answer

>Encapsulation is a fundamental concept in object-oriented programming (OOP) that refers to the practice of keeping the internal state and behavior of an object hidden from the outside world, and only exposing a public interface that can be used to interact with the object. The main goal of encapsulation is to protect the integrity of the object's internal state and to hide the implementation details of the object from the outside world.

>Encapsulation is typically achieved through the use of access modifiers (such as public, private, protected, etc.) that control the visibility of the object's properties and methods. For example, a class can have a private field that represents the internal state of the object, and a public method that allows other objects to access or modify the internal state of the object in a controlled and predictable way.

>Encapsulation provides several benefits such as:

>It allows the developer to change the implementation of an object without affecting the code that uses the object.
It helps to isolate the effects of changes, making the system more robust and less prone to errors.
It promotes the use of a clear and consistent interface for interacting with the object, making the code more readable and maintainable.
It allows the developer to implement security mechanisms, such as access control, to prevent unauthorized access to the object's internal state and behavior.
It is important to note that encapsulation is not about hiding information, it is about controlling the access to the information and keeping the object's internal state and behavior consistent and predictable.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>

## 4. What is inheritance
### Answer

>Inheritance is a fundamental concept in object-oriented programming (OOP) that allows one class to inherit the properties and methods of another class, allowing for code reuse and a more hierarchical organization of code. The class that inherits from another class is called a derived class, and the class from which it inherits is called a base class.

>The main advantage of inheritance is that it allows a developer to create new classes that are based on existing classes, without having to rewrite the same code. The derived class inherits all of the properties and methods of the base class, and can also add new properties and methods or override existing ones.

>For example, let's consider that you have a Vehicle class that has properties such as Make, Model, Year and methods such as Start(), Stop(), Accelerate() and you want to create a Car class that inherits from the Vehicle class, the Car class will have all properties and methods of the Vehicle class plus the additional properties and methods that are specific to cars such as NumberOfDoors, NumberOfSeats, etc.

>Inheritance also allows for a more hierarchical organization of code, where a base class represents a general concept and derived classes represent more specific concepts. This makes it easier to understand and maintain the code, as the developer can easily see the relationship between classes and understand how the code is organized.

>Inheritance is one of the fundamental concepts of OOP, and it is supported by most modern programming languages, including Java, C#, Python, and many more. It's important to note that Inheritance is just one way of achieving code reuse, other ways of code reuse are composition and interfaces.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>


## 1. What is technical debt
### *Answer*

> Technical debt refers to the cost of maintaining and enhancing software over time. It is a metaphor used to describe the trade-off between investing in short-term workarounds, quick-fixes, and other shortcuts to meet immediate needs, and investing in more robust, long-term solutions that may require more time and resources up front.
The idea is that, just as financial debt incurs interest, technical debt incurs "interest" in the form of extra effort that must be expended in the future to maintain or enhance the software. This extra effort can come in the form of additional development work, increased testing, or higher maintenance costs.
The goal is to minimize technical debt by designing and building software in a maintainable and scalable way, so that it can be easily updated and extended as business needs change. This is important because as the technical debt increases, it can become harder and more expensive to make changes to the software, which can slow down development and impact the business.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Basic Knowledge             |                 |
| **L2**    | General Knowledge           |                 |
| **L3**    | Stron in Depth Knowledge    |                 |
---
<br/><br/>
<h1 align="center"> Language</h1>
<br/><br/>

## 1. Are you familiar with async and await keywords in C#? What they are used for? How they work under the hood? What is the difference between this and multithreading?
### Answer
>`async` and `await` are C# language keywords that allow you to write asynchronous code that is easy to read and understand. Under the hood, they work by using a combination of the `Task` and `Task<T>` classes and the async and await operators to represent and manipulate asynchronous operations.

>When a method is marked with the async keyword, it is converted to a method that returns a `Task` or `Task<T>` object. This object represents the asynchronous operation that is being performed by the method. The method can then use the await keyword to suspend its execution until an asynchronous operation has completed.

>When the await keyword is encountered, the runtime checks the object being awaited to see if it is already completed. If it is, execution continues normally. If it is not, the method's execution is suspended, and the runtime schedules the method to be resumed when the awaited task completes.

>When the awaited task completes, the runtime resumes the execution of the method where it was suspended. The method then continues to execute until it reaches another await or until it completes. If the method completes, the returned `Task` or `Task<T>` object is set to the completed state, and any continuations waiting on the task are scheduled to be executed.

>In summary, `async/await` allows C# developer to write asynchronous code that is similar to synchronous code, The async keyword indicate that a method has asynchronous operations, and the await keyword lets the method to wait for the completion of an asynchronous operation before continuing. This is useful for writing code that performs multiple, concurrent tasks that don't block each other.

>Asynchronous programming refers to the ability to execute a long-running operation without blocking the calling thread, and without creating a new thread. Instead of blocking the thread, the operation is executed asynchronously, allowing the thread to continue executing other code while waiting for the operation to complete. Asynchronous programming in C# can be implemented using the async and await keywords, and is typically used for I/O-bound operations, such as network requests or disk I/O.

>On the other hand, multithreading refers to the ability to execute multiple threads concurrently within the same process or application. Each thread runs independently of the other threads, and can perform its own tasks simultaneously. Multithreading in C# can be implemented using the Thread class, or other higher-level abstractions such as the Task or ThreadPool classes. Multithreading is typically used for CPU-bound operations, such as heavy calculations or processing tasks that can benefit from parallelization.

>In summary, asynchronous programming is a way to perform long-running I/O operations without blocking the calling thread, while multithreading is a way to perform CPU-bound operations concurrently using multiple threads. Asynchronous programming is generally used for I/O-bound operations, while multithreading is generally used for CPU-bound operations.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciptions         |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | Describes how it works under the hood |
---
<br/><br/>

## 2. What is extension method? How it is used? How to create one?
### Answer

>An extension method in C# is a method that is added to an existing type, such as a class or interface, but is implemented as a separate static method. Extension methods allow you to add new methods to existing types without modifying the original source code. The `this` keyword is used to specify the type that the extension method is being added to, and the method is called as if it were an instance method on the type.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciptions         |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 3. What is the difference between `StringBuilder` and `String`?
### Answer
> Strings are immutable, and you cannot modify it. Every time you want to modify it new instance is created. String builder is mutable. You don’t need to create a new instance when you want to modify it. String Builder has better performance

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciptions         |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 4. What is Reflection?
### Answer
> Reflection is a feature of language that allows a program to examine its own structure, including types, methods, properties, and fields, at runtime. It allows to discover and use information about an assembly, such as the types it contains, at runtime, rather than at compile time.
Reflection makes it possible to write more generic and flexible code, but it also comes with a performance cost. Because reflection is typically used at runtime, it can add a significant overhead to your application.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciptions         |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 5. What is boxing and unboxing?
### Answer
>Boxing is the process of converting a value type to a reference type. This is done by creating a new object on the heap that contains the value of the value type, and storing a reference to that object in a variable of the reference type.

> Unboxing is the reverse process, where a reference type is converted back to a value type. This is done by extracting the value of the object and storing it in a variable of the value type.

> In order to convert a reference type back to a value type, you must use a cast operator, whereas when converting a value type to a reference type, the conversion is done automatically. This is because the C# compiler can't know if the conversion will lose any data and it is safer to make the programmer explicit about the unboxing operation.
```C#
int i = 42;
object o = i;  // Implicit boxing

int j = (int)o;  // Explicit unboxing
```

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | No Answer                   |                 |
| **L2**    | Right Answer                |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 6. What are value and reference types? Are value types always stored in Stack?
### Answer
> Value types are typically stored on the stack, but they can also be stored on the heap if they are inside a reference type, such as an object. In C# and other languages that implement the Common Language Infrastructure, value types are allocated on the stack when they are defined as local variables, method parameters, or fields of a struct. However, when they are fields of a class or when they are boxed, they are allocated on the heap.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Description         |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | Knows that value not always stored in Stack and can describe in depth                |
---
<br/><br/>

## 7. What is the difference between constant and readonly?
### Answer
>Constants are evaluated at compile time, while the read-only variables are evaluated at run time. 

>Constants support only value-type variables (the only exception being strings), while read-only variables can hold reference-type variables. 

>Constants should be used when the value is not changing during run time, and read-only variables are used mostly when their actual value is unknown before run time. 

>Read-only variables can only be initialized at the time of declaration or in a constructor.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Right Answer                |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 8. What is `using` block and IDisposable?
### Answer
> The using block is a C# construct that is used to ensure that a specific resource, such as a file or a database connection, is properly disposed of when it is no longer needed. The using block creates a new scope and automatically calls the Dispose method on an object when the block is exited. This can help to prevent resource leaks and ensure that resources are freed in a timely manner.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Right Answer                |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | Mentions that under the hood it is just a try catch finally block, where Dispose is called in the finally block |
---
<br/><br/>

## 9. What is interface: What is the difference between interface and abstract class?
### Answer
> An interface in C# and other programming languages is a contract that defines a set of methods, properties, and events that a class must implement. It is a way to specify a common set of functionality that multiple classes can implement, without specifying the implementation details.

> An abstract class, on the other hand, is a class that cannot be instantiated and is meant to be a base class for other classes. An abstract class can provide a default implementation for some or all of its methods, properties, and events. An abstract class can also define and implement an interface.

> The main difference between an interface and an abstract class is that a class can implement multiple interfaces, but it can only inherit from one abstract class. An interface defines a contract, and a class can choose to implement that contract, whereas an abstract class is a blueprint for a class, and a derived class must inherit from it.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciption          |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 10. What is delegate?
### Answer
> Using a delegate allows the programmer to encapsulate a reference to a method inside a delegate object. The delegate object can then be passed to code which can call the referenced method, without having to know at compile time which method will be invoked. In addition, we could use delegate to create custom event within a class 

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciption          |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | Describes how it works under the hood |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | ↑↑↑↑↑↑↑↑↑↑↑↑↑ |
---
<br/><br/>

## 11. What is lambda expression?
### Answer
>A lambda expression is a shorthand notation for defining an anonymous function in C# and other programming languages that support functional programming. A lambda expression is a way to create a small, inline function without having to give it a name or define it in a separate method.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciption          |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 12. What is the difference between overriding and overloading?
### Answer
>In C#, overriding and overloading are both mechanisms that allow you to create multiple methods with the same name, but they have different purposes and characteristics.

>Method overriding is a feature of object-oriented programming that allows a derived class to provide a specific implementation of a method that is already defined in its base class. When a method in a derived class has the same name, return type, and parameter list as a method in its base class, it is said to override the base class method. The derived class method is said to be **overriding** the base class method.

>Method overloading, on the other hand, is a feature that allows you to create multiple methods with the same name but with different parameter lists within the same class or struct. When a class or struct has multiple methods with the same name but different parameter lists, it is said to have overloaded methods.

>In summary, overriding allows a derived class to provide a specific implementation of a method that is already defined in its base class, while overloading allows you to create multiple methods with the same name but with different parameter lists within the same class or struct.

>It's important to note that in order for a method to be overridden, the method in the base class must be marked as virtual, abstract or override-able. Overloaded methods do not need any special keyword to be used, they just need to have the same name but different parameters.

> Basically one is compile time polymorphism and the other one is run time polymorphism. Also should describe how to achieve both 

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciption          |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               | Mentions last point |
---
<br/><br/>

## 13. Can you explain the difference between an abstract class and a sealed class in C#?
### Answer
>An abstract class is a class that cannot be instantiated and is typically used as a base class for other classes, while a sealed class is a class that cannot be inherited.

>In C#, an abstract class and a sealed class are both used in object-oriented programming, but they serve different purposes and have different characteristics.

>An abstract class is a class that cannot be instantiated and is meant to be a base class for other classes. An abstract class is declared using the `abstract` keyword and can have both abstract and non-abstract methods. Abstract methods are methods that do not have an implementation and must be overridden by the derived classes. Abstract classes can have constructors and can have fields and properties.

>A sealed class, on the other hand, is a class that cannot be inherited by other classes. A sealed class is declared using the `sealed` keyword and can have both sealed and non-sealed methods. A sealed class can have constructors and can have fields and properties.

>In summary, an abstract class is a class that cannot be instantiated and is meant to be a base class for other classes, while a sealed class is a class that cannot be inherited by other classes. An abstract class can have abstract methods that must be overridden by the derived class, while a sealed class cannot have derived classes.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciption          |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 14. What is dependency injection in and what are the benefits of using it? How to implement it?
### Answer
>Dependency injection (DI) is a design pattern that allows a class to receive its dependencies (objects it depends on) from an external source rather than creating them itself. It helps to decouple the class from its dependencies, making the class more flexible, testable, and maintainable.

>There are several benefits to using dependency injection:

* **Loose coupling**: Classes are not tightly coupled to their dependencies, which makes them more flexible and easier to change.
* **Improved testability**: Classes can be easily unit-tested as their dependencies can be easily mocked or substituted.
* **Better maintainability**: Classes are easier to understand, maintain, and extend as their dependencies are clearly defined and can be changed independently.

>There are several ways to implement dependency injection in C#. One of the most popular ways is to use an Inversion of Control (IoC) container. An IoC container is a library that manages the creation and lifecycle of objects and their dependencies. Some popular IoC containers for C# are `Autofac`, `Ninject`, and `Unity`.

>To use an IoC container, you need to register your types and their dependencies with the container. For example, using Autofac:
```C#
var builder = new ContainerBuilder();

builder.RegisterType<MyClass>().As<IMyInterface>();
builder.RegisterType<MyDependency>().As<IMyDependency>();

var container = builder.Build();
```
>You can then use the container to resolve instances of your classes, and it will automatically resolve their dependencies. For example, using `Autofac`:
```C#
var myClass = container.Resolve<IMyInterface>();
```
>Another way to implement dependency injection in C# is through the use of interfaces, constructor injection and property injection. This can be done by creating an interface which defines the dependencies and then passing those dependencies through the constructor or properties while creating the class instance.

>Overall, Dependency injection is a powerful technique that can help make your code more flexible, testable, and maintainable. There are several ways to implement it in C#, but using an IoC container is one of the most popular and easiest ways to do so.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciption          | Probably not mentions advantages |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 15. Can you explain the difference between an array and a list in C#?
### Answer
>In C#, an Array and a List are both used to store a collection of items, but there are some differences between the two.

>An array is a fixed-size collection of items of a specific data type. Once an array is created, its size cannot be changed. Arrays are created using the `new` keyword, followed by the data type and the size of the array in square brackets. For example:
```C#
int[] numbers = new int[10];
```
>A List, on the other hand, is a dynamic-size collection of items that can grow or shrink as needed. A List is created using the generic `List<T>` class, where `T` is the data type of the items. For example:
```C#
List<int> numbers = new List<int>();
```
>In summary, an array is a fixed-size collection of items that cannot be resized, while a List is a dynamic-size collection of items that can be resized as needed.

>Additionally, `List` class have more methods than arrays like `Add`, `Remove`, `Insert`, etc which makes it more powerful than arrays. Lists are also less memory efficient than arrays because they have an overhead of storing the size of the list, while arrays do not.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | General Desciption          |                 |
| **L2**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 16. Can you explain the difference between a `Hashtable` and a `Dictionary` in C#?
### Answer
>In C#, a `Dictionary` is a generic collection class that maps keys to values, similar to a hash table. However, there are some differences between the two.

>A `Hashtable` is a non-generic collection class that was introduced in the first version of .NET Framework. It stores key-value pairs where the key must be an object, and the value can be any object. It is thread-safe, which means that multiple threads can read and write to it simultaneously without any data corruption.

>A `Dictionary`, on the other hand, is a generic collection class that was introduced in the second version of the .NET Framework. It stores key-value pairs where the key and value can be of any data type. It is not thread-safe, which means that if multiple threads access it simultaneously, there is a possibility of data corruption.

>In summary, both `Hashtable` and `Dictionary` are used to store key-value pairs, but a `Dictionary` is a generic version of `Hashtable`, and `Dictionary` is not thread-safe.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Don't know                  |                 |
| **L2**    | Maybe knows answer          |                 |
| **L3**    | Right answer                |                 |
---
<br/><br/>

## 17. Can you explain the difference between a constructor and a static constructor in C#?
### Answer
>In C#, a constructor is a method that is called when an object of a class is created. It is used to initialize the state of the object and allocate memory for it. A constructor does not have a return type and has the same name as the class.

>A static constructor, on the other hand, is a special type of constructor that is used to initialize the static fields of a class. It is called only once when the class is first loaded by the runtime and before any instance of the class is created. A static constructor does not have a return type and has the same name as the class preceded by the keyword `static`.

>The main difference between a constructor and a static constructor is that a constructor is called every time an object of a class is created, while a static constructor is called only once when the class is first loaded by the runtime. Also, a constructor can have parameters while a static constructor cannot have any parameters.

>A constructor is used to initialize an instance of a class while a static constructor is used to initialize a class and its static fields.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Don't know                  |                 |
| **L2**    | Maybe knows answer          |                 |
| **L3**    | Right answer                |                 |
---
<br/><br/>
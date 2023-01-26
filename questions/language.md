<h1 align="center"> Language</h1>
<br/><br/>

## 1. Are you familiar with async and await keywords in C#  
### Answer
| **Level** | **Expectaions** |
|-----------|-------------|
| **L1, L2** | Should have used these keywords in code. Should know why they use for       |
| **L3**    | Should be able to describe how async, await work under the hood          |

## 2. What is extension method 
### Answer

>An extension method in C# is a method that is added to an existing type, such as a class or interface, but is implemented as a separate static method. Extension methods allow you to add new methods to existing types without modifying the original source code. The "this" keyword is used to specify the type that the extension method is being added to, and the method is called as if it were an instance method on the type.

| **Level** | **Expectaions, Grade** |
|-----------|-------------|
| **L1**    | 10          |
| **L2**    | 10          |
| **L3**    | 10          |


## 3. What is the difference between String Builder and String 
### Answer
> Strings are immutable, and you cannot modify it. Every time you want to modify it new instance is created. String builder is mutable. You don’t need to create a new instance when you want to modify it. String Builder has better performance

| **Level** | **Expectaions, Grade** |
|-----------|-------------|
| **L1**    | 5           |
| **L2**    | 10          |
| **L3**    | 10          | 


## 4. What is Reflection
### Answer
> Reflection is a feature of language that allows a program to examine its own structure, including types, methods, properties, and fields, at runtime. It allows to discover and use information about an assembly, such as the types it contains, at runtime, rather than at compile time.
Reflection makes it possible to write more generic and flexible code, but it also comes with a performance cost. Because reflection is typically used at runtime, it can add a significant overhead to your application.

| **Level** | **Expectaions, Grade** |
|-----------|-------------|
| **L1**    | 3           |
| **L2**    | 8           |
| **L3**    | 10          |


## 5. What is boxing and unboxing 
### Answer
> Boxing is the process of converting a value type to a reference type. This is done by creating a new object on the heap that contains the value of the value type, and storing a reference to that object in a variable of the reference type.
>  
> Unboxing is the reverse process, where a reference type is converted back to a value type. This is done by extracting the value of the object and storing it in a variable of the value type. For example:
> 
> in order to convert a reference type back to a value type, you must use a cast operator, whereas when converting a value type to a reference type, the conversion is done automatically. This is because the C# compiler can't know if the conversion will lose any data and it is safer to make the programmer explicit about the unboxing operation.
```C#
int i = 42;
object o = i;  // Implicit boxing

int j = (int)o;  // Explicit unboxing
```

| **Level** | **Expectaions, Grade** |
|-----------|-------------|
| **L1**    | 3           |
| **L2**    | 8           |
| **L3**    | 10          |


## 6. Are value types always stored in Stack 
### Answer
> Value types are typically stored on the stack, but they can also be stored on the heap if they are inside a reference type, such as an object. In C# and other languages that implement the Common Language Infrastructure, value types are allocated on the stack when they are defined as local variables, method parameters, or fields of a struct. However, when they are fields of a class or when they are boxed, they are allocated on the heap.

| **Level** | **Expectaions, Grade** |
|-----------|-------------|
| **L1**    | 1           |
| **L2**    | 3           |
| **L3**    | 9           |


## 7. What is the difference between constant and readonly 
### Answer
> Constants are evaluated at compile time, while the read-only variables are evaluated at run time. 

> Constants support only value-type variables (the only exception being strings), while read-only variables can hold reference-type variables. 

> Constants should be used when the value is not changing during run time, and read-only variables are used mostly when their actual value is unknown before run time. 

> Read-only variables can only be initialized at the time of declaration or in a constructor.

| **Level** | **Expectaions, Grade** |
|-----------|-------------|
| **L1**    | 0           |
| **L2**    | 0           |
| **L3**    | 0           |

## 8. What is using block and IDisposable  
### Answer
> The using block is a C# construct that is used to ensure that a specific resource, such as a file or a database connection, is properly disposed of when it is no longer needed. The using block creates a new scope and automatically calls the Dispose method on an object when the block is exited. This can help to prevent resource leaks and ensure that resources are freed in a timely manner.
> 
> **Under the hood it is just a try catch finally block, where Dispose is called in the finally block**

| **Level** | **Expectaions, Grade** |
|-----------|-------------|
| **L1**    | 0           |
| **L2**    | 0           |
| **L3**    | 0           |


## 9. What is interface: What is the difference between interface and abstract class 
### Answer
> An interface in C# and other programming languages is a contract that defines a set of methods, properties, and events that a class must implement. It is a way to specify a common set of functionality that multiple classes can implement, without specifying the implementation details.

> An abstract class, on the other hand, is a class that cannot be instantiated and is meant to be a base class for other classes. An abstract class can provide a default implementation for some or all of its methods, properties, and events. An abstract class can also define and implement an interface.

> The main difference between an interface and an abstract class is that a class can implement multiple interfaces, but it can only inherit from one abstract class. An interface defines a contract, and a class can choose to implement that contract, whereas an abstract class is a blueprint for a class, and a derived class must inherit from it.

| **Level** | **Expectaions, Grade** |
|-----------|-------------|
| **L1**    | 0           |
| **L2**    | 0           |
| **L3**    | 0           |


## 10. What is delegate 
### Answer
> Using a delegate allows the programmer to encapsulate a reference to a method inside a delegate object. The delegate object can then be passed to code which can call the referenced method, without having to know at compile time which method will be invoked. In addition, we could use delegate to create custom event within a class 

| **Level** | **Expectaions, Grade** |
|-----------|-------------|
| **L1**    | 0           |
| **L2**    | 0           |
| **L3**    | 0           |


## 11. What is lambda expression 
### Answer
> A lambda expression is a shorthand notation for defining an anonymous function in C# and other programming languages that support functional programming. A lambda expression is a way to create a small, inline function without having to give it a name or define it in a separate method.

| **Level** | **Expectaions, Grade** |
|-----------|-------------|
| **L1**    | 0           |
| **L2**    | 0           |
| **L3**    | 0           |



## 12. What is the difference between overriding and overloading 
### Answer
> Basically one is compile time polymorphism and the other one is run time polymorphism. Also should describe how to achieve both 

| **Level** | **Expectaions, Grade** |
|-----------|-------------|
| **L1**    | 0           |
| **L2**    | 0           |
| **L3**    | 0           |
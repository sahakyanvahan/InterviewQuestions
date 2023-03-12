<h1 align="center"> Testing </h1>
<br/><br/>

## 1. Are you familiar with FIRST principles of Unit testing?
### Answer
>The FIRST principles of unit testing are a set of guidelines that can help you write high-quality, effective unit tests. The acronym "FIRST" stands for:

> * **Fast:** Unit tests should be fast and run quickly, allowing you to run them frequently as part of your development process.
> * **Independent:** Unit tests should be isolated from each other, with no dependencies on the results of other tests. This ensures that tests can be run in any order, and that the failure of one test does not affect the outcome of other tests.
> * **Repeatable:** Unit tests should produce the same results every time they are run, regardless of the environment or state of the system.
> * **Self-Validating:** Unit tests should have clear and verifiable outcomes, making it easy to determine whether the test has passed or failed.
> * **Timely:** Unit tests should be written and run in a timely manner, as close as possible to the development of the corresponding code. This helps to catch errors early in the development process, when they are easier and less expensive to fix.

>By following the FIRST principles, you can write unit tests that are efficient, reliable, and effective in detecting errors in your code. This can help you to maintain a high-quality codebase, reduce the risk of bugs and regression, and improve your overall development process.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Don't know                  |                 |
| **L2**    | General Desciptions         |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 2. Do you know what is testing pyramid?
### Answer
>The testing pyramid is a visual representation of the different types of tests that should be used in software development and the relative proportion of each type. It is called a "pyramid" because the tests are arranged in layers, with more tests at the bottom (unit tests) and fewer tests at the top (end-to-end tests).

>The testing pyramid consists of the following types of tests:

> * **Unit Tests:** These are the most numerous tests, and they test individual components or functions in isolation. They are fast, automated, and reliable, and they are used to validate the basic functionality of the code.

> * **Integration Tests:** These tests test the interactions between different components, to ensure that they work together as expected. They are still automated, but they take longer to run and are more complex than unit tests.

> * **End-to-End Tests:** These tests test the entire system, from end-to-end, to ensure that everything works as expected. They are slower, more complex, and more brittle than the other types of tests, and they are used to validate the overall functionality of the system.

>The goal of the testing pyramid is to provide a balance between the different types of tests, so that you can validate the functionality of the system with a minimum of tests, while still covering all the important aspects of the system. By following the testing pyramid, you can ensure that your tests are fast, reliable, and effective, and that you are not spending too much time on slow and complex tests that add little value.

>It's worth noting that the testing pyramid is a guideline, not a strict rule, and there may be cases where you need to deviate from the pyramid, depending on the specific requirements of your project. However, in general, following the testing pyramid can help you to write effective and efficient tests for your software.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | Don't know                  |                 |
| **L2**    | General Desciptions         |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 3. What is the difference between NUnit and XUnit 
### Answer
>One of the main differences is the syntax for writing tests. NUnit uses a more traditional, attribute-based syntax for marking test methods, while xUnit uses a more fluent, method-based syntax. For example, in NUnit, a test method is marked with the [Test] attribute, while in xUnit, it is marked with the [Fact] attribute.

>Another difference is that xUnit is designed to be more extensible and modular than NUnit. xUnit uses a more composable architecture, which allows developers to create their own custom test runners, test discoverers, and other components.

>Another difference is the way how they handle test discovery and execution. NUnit loads all the tests in an assembly at once and then runs them, xUnit uses a more dynamic approach, it only loads the tests that are going to be executed, this could be an advantage when dealing with large test suites.

>Additionally, xUnit has some features that are not present in NUnit. For example, xUnit has built-in support for test theories (tests that are parameterized with multiple sets of data) and collection fixtures (shared context for tests in a test collection).

>NUnit creates an instance of test class for each method while XUnit creates one instance of a class for all methods in that class 

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | No Answer                   |                 |
| **L2**    | General Answer              | Mentions last point |
| **L3**    | General Answer              | Mentions other points as well |
---
<br/><br/>

## 4. What is TDD? Pros and Cons. 
### Answer
> Test-Driven Development (TDD) is a software development methodology where the development of software is done through a repeated process of writing test cases before writing the code and then writing just enough code to pass the tests. The cycle of writing tests, writing code, and refactoring the code continues until the software meets all the requirements.
> 
> ### **Pros:**
> * **Improved code quality:** By writing tests first, developers can ensure that the code meets the requirements and works as intended.
> * **Early detection of bugs:** Tests help to catch bugs early in the development process, making it easier and quicker to fix them.
> * **Better design:** The process of writing tests can help to reveal design flaws and improve the overall design of the code.
> * **Increased confidence:** With a comprehensive suite of tests, developers can feel confident in making changes to the code without introducing new bugs.

> ### **Cons:**
> * **Time-consuming:** Writing tests takes time, which can be a drawback, especially in fast-paced development environments.
> * **Overhead:** The process of TDD can add an additional layer of complexity to the development process.
> * **Resistance to change:** TDD requires a change in mindset and approach to software development, which can be difficult for some developers to adopt.

> ### **Best practices:**
> * **Write tests first:** Always write tests before writing the code, to ensure that the code meets the requirements and works as intended.
> * **Keep tests simple:** Tests should be simple, focused, and fast. Avoid complex test setups and keep tests independent of each other.
> * **Automate tests:** Automate as many tests as possible to save time and ensure consistency.
> * **Refactor code regularly:** Regularly refactor code to keep it clean and maintainable.
> * **Prioritize tests:** Prioritize tests based on the criticality of the code. Write tests for the most critical parts of the code first.
> * **Write meaningful test names:** Test names should clearly describe what the test is doing, making it easier to understand the intent of the test

>The "Red-Green-Refactor" approach is a common practice in Test-Driven Development (TDD). It involves writing a failing test first, and then writing the minimum amount of code necessary to make the test pass. Finally, you refactor the code to make it clean, maintainable, and efficient.

>Here's how the "Red-Green-Refactor" approach works in detail:

> * **Red:** Write a failing test case for the new functionality you want to add. The test should express the desired behavior of the code, and should initially fail because the functionality hasn't been implemented yet.

> * **Green:** Write the minimum amount of code necessary to make the test pass. This should be the bare minimum implementation, with no frills or unnecessary complexity.

> * **Refactor:** Once the test is passing, clean up the code, making it readable, maintainable, and efficient. You can also add additional tests if necessary to ensure the code works as expected.

>This approach helps you focus on writing code that works, and not just code that compiles. It also helps you ensure that your code is well-designed, readable, and maintainable, as you are forced to think about the design and implementation of the code before writing it.

>In TDD, the "Red-Green-Refactor" approach is repeated for each new feature or change you want to make to the code. This results in a suite of tests that provide a safety net for your code, making it easier to catch and fix bugs, and ensuring that new changes don't break existing functionality.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | No Answer                   |                 |
| **L2**    | Right Answer                |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 5. How to test private methods 
### Answer

>The best practice for testing private methods in C# is to focus on testing the public API of a class, and not rely on the implementation details of private methods. This results in a cleaner design, better code maintainability, and more robust tests.

> * **Reflection:** You can use the Reflection API to access private methods and invoke them. Reflection allows you to dynamically inspect and interact with types and members of an assembly, including private methods.
>
> With `PrivateObject`, you can access and invoke private methods, properties, and fields of a class. It is especially useful when you need to test code that has tight coupling between the implementation and the private methods.
>Here's an example of how to use `PrivateObject` to test a private method:

``` C#
using Microsoft.VisualStudio.TestTools.UnitTesting;

[TestClass]
public class MyClassTests
{
    [TestMethod]
    public void TestPrivateMethod()
    {
        var myClass = new MyClass();
        var privateObject = new PrivateObject(myClass);

        int result = (int)privateObject.Invoke("PrivateMethod", 42);

        Assert.AreEqual(84, result);
    }
}
```

>In this example, we create an instance of the `PrivateObject` class, passing in an instance of the `MyClass` class. Then, we use the `Invoke` method of the `PrivateObject` class to access and invoke the private method `PrivateMethod`, passing in an argument of 42. Finally, we use an `Assert` statement to verify that the result of the invocation is 84.

>It's important to note that relying on `PrivateObject` to test private members of a class goes against the principles of unit testing, as it tightly couples the tests to the implementation details of the class. It's better to refactor the code and test the public API of the class instead, whenever possible.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | No Answer                   |                 |
| **L2**    | Right Answer                |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>
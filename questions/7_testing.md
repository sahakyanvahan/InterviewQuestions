<h1 align="center"> Testing </h1>
<br/><br/>
test
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

## 5. Are you familiar with mutations testing?
### Answer
> Mutation testing is a software testing technique that involves introducing small changes, called mutations, to the code in order to test the effectiveness of the existing tests. The idea is to create artificial faults or defects in the code, and then run the test suite to see if it can detect the faults.

> In mutation testing, the tester uses a tool to automatically generate small variations, or mutations, of the code. The mutations are typically simple changes such as swapping the order of two statements, replacing an operator with another, or inserting a logical negation.

> Once the mutations are generated, the tool runs the existing test suite against each mutated version of the code. If the test suite can detect the mutation, it means the mutation is "killed". If the test suite fails to detect the mutation, it means the mutation "survived" and indicates a gap in the test suite.

> Mutation testing is a powerful technique for evaluating the quality of a test suite. It helps to identify gaps in the test suite, such as weak or missing assertions, and can help improve the overall quality of the code by detecting defects that may have gone undetected otherwise.

> During mutation testing, the score is a metric that represents the effectiveness of the test suite in detecting mutations. The score is calculated as the ratio of the number of mutations that were killed by the test suite to the total number of mutations that were generated.

> A high mutation score indicates that the test suite is effective in detecting faults in the code. A low mutation score indicates that there are gaps in the test suite that need to be addressed.

> The mutation score is typically used as a measure of the quality of the test suite. A high mutation score can give developers confidence that the test suite is effective in detecting faults, while a low mutation score can indicate that further testing is needed.

> It's worth noting that while a high mutation score is desirable, it doesn't necessarily guarantee that the test suite is perfect or that the code is bug-free. Mutations are a simplification of the types of faults that can occur in code, and it's possible for some faults to go undetected by the test suite even if the mutation score is high. As such, mutation testing should be used as part of a broader testing strategy that includes other techniques such as unit testing, integration testing, and manual testing.

> **There are several tools available for implementing mutation testing in C#. Some popular tools include:**

> **Stryker.NET:** Stryker.NET is a mutation testing framework for .NET applications. It supports C# and VB.NET and integrates with popular test frameworks like NUnit and MSTest. Stryker.NET can automatically generate and run mutations, and provides a dashboard for visualizing the results.

> **NinjaTurtles:** NinjaTurtles is another mutation testing tool for .NET applications. It supports C# and VB.NET and integrates with test frameworks like NUnit and xUnit. NinjaTurtles can automatically generate mutations and provides a simple command-line interface for running the tests and analyzing the results.

> **PITest:** PITest is a mutation testing tool for Java applications, but it also supports C# through the use of the Sharpen tool. PITest can automatically generate and run mutations, and provides a dashboard for visualizing the results.

> To use these tools, you typically need to include them as a dependency in your project and configure them to work with your test framework. Once the tool is configured, you can run the mutation testing process, which involves generating mutations, running the test suite against the mutated code, and analyzing the results.

| **Level** | **Expectaions**             | **Notes**       |
|-----------|-----------------------------|-----------------|
| **L1**    | No Answer                   |                 |
| **L2**    | Right Answer                |                 |
| **L3**    | ↑↑↑↑↑↑↑↑↑↑↑↑↑               |                 |
---
<br/><br/>

## 6. How to test private methods 
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
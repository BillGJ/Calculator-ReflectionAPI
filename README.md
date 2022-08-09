# Calculator - Exercise: Reflection API

This program is intended to be an in-house unit testing framework that uses the Reflection API

I have defined the `@Test` annotation to mark unit test methods 
and I have created the `UnitTest` interface, which provides two abstract methods:

* `void beforeEachTest()` which runs before each test to setup the test environment
*  `void afterEachTest()` which runs after each test to clean up the test environment

## Reflection Api

The reflection API to do the following:

1. Make sure the test class implements UnitTest
2. Create an instance of the test class and cast it to be a UnitTest
3. For each method with the @Test annotation:
   * Call `UnitTest#beforeEachTest()`, then invoke the test method (use Method#invoke()), 
   and then call `UnitTest#afterEachTest()`.
   * If the test threw any errors, record that test as having failed.
   Otherwise, record that test as having passed.


## Compiling and Running

    javac -cp . TestRunner.java
    java -ea -cp . TestRunner

*Note:* See the `-ea` JVM option? That stands for "enable assertions", 
which makes the assert statements in `CalculatorTest.java` actually throw `AssertionErrors`. 
There are much more robust assertion libraries out there, 
but for the purposes of this exercise, assert keeps things simple.

After running the program, the output should be similar to this:

    Passed tests: [CalculatorTest#testAddition]
    FAILED tests: [CalculatorTest#testSubtraction]
---
title: Kotlin - Methods, Exception and Error Handiling
description: Kotlin - Methods, Exception and Error Handiling
class: gaia
_class:
  - lead
  - invert
style: |
    #img-right{
      float: right;
    }
     img[alt~="center"] {
      display: block;
      margin: 0 auto;
    }
    table {
      border-collapse: collapse;
      font-size: 22px;
    }
    table, th,tr, td {
      border: none!important;
      vertical-align: middle;
    }
size: 16:9
paginate: true
_paginate: false
marp: true
math: true
---

# Functions/Methods, Exception and Error Handiling

    Course Code: ELEE1146 

    Course Name: Mobile Applications for Engineers

    Credits: 15

    Module Leader: Seb Blair BEng(H) PGCAP MIET MIEEE MIHEEM FHEA

---

## Method vs Function

**Method**: a set of instructions that are associated with an object.
```kt
var s: String = "some string"

s.toCharArray() 
```

**Function**: a set of instructions that perform a task.
```kt
fun concatName(firstName : String, middleName: String, lastName: String) : String {
    return "$firstName $middleName $lastName"
}

val fullName : String = concatName("Marshall", "Bruce", "Mathers")
```
---

## Function

- **Function Definition** 
  - Specifies what the method is doing and how to use it consists of method declaration and method body does not execute the statements specified in the method body!
  
-  **Function Invocation (Call)**
   -  specifies how the method should be used (invoked, called) in another method
actually executes the method statements with method arguments provided

---

## Function Definition

- **Function Declaration contains:**
  - access modifiers – optional
  - return type - optional
  - the method identifier 
  - any legal identifier name (Camel case)
    - method arguments (if present) enclosed in brackets  `(` and `)`
    - even when the method have no arguments you must still keep the brackets

- **Function Body:**
  - Enclosed in braces `{` and `}`
  - Consists of statements that specify what the method is doing

---


## Function Anatomy

```
FUNCTION HEADER
<visibility modifiers>[fun keyword][function name]<(function parameters)><:return type>
{
  ...                  FUNCTION BODY
  <return type>
}
```

**Example**

```kt
private fun myFunction(s: String, n: Int) : Boolean
{
  ...
  return Boolean
}
```

---

## Function Body Block

<div style="font-size: 26px">

- Function body is a block of code where declarations and/or statements are enclosed in 
`{` and `}`.

- If the Function returns a value, e.g. the method *returnValue* then the statement `return expression` should be present in the method body.
  
- The expression type in the `return` statement must be the same as the *returnType* – casting rules apply.

</div >

```kt
private fun myFunction(s: String, n: Int) : Boolean
{
  if(s.toIntOrNull() != null && s.toIntOrNull() == n ){
      return true
  }
  else {
      return false
  }
}
```
---

## Function Innvocation (to call)

- **Function invocation (call)**
  - Actually executes the statements in the body of the function
  - `functionName` ( [argument list] )
    - the values passed as arguments should have the same type as specified in the function declaration - casting rules 

  ```kt
  fun concatNameAndAge(firstName : String, middleName: String, lastName: String, age: Int) : String 
  {
      return "$firstName $middleName $lastName : $age:"
  }

  val fullName : String = concatName("Marshall", "Bruce", "Mathers", (25.0).toInt)
  ```
---


## Function Innvocation 2

- **Function definition**
```kt
fun assessment( assessmentOne: Byte, assessmentTwo: Byte ) : Double
{
    return ( (0.3 * assessmentOne) + (0.7 * assessmentTwo) )
}
``` 

- **Function call**
 
```kt
print("Your module result is:  $assessment(45, 55))
```
<details>
<summary>What will be displayed</summary>

`The result of the assessment of the course is: 52.0`

</summary>

---


## Function Innovation 3

- **Function Definition**
  ```kt
  internal private fun printResult( s1 : String, i1 : Int, s2 : String, i2: Int )
  {
      println( "$s1 : $i1, $s2 : $i2");
  }
  ``` 

  <!--
  internal means that the declarations are visible inside the module only 
  -->

- **Function Call**

  ```kt
  printResult("First number", -25, "second number", 10);
  ```

  <details>
  <summary>What will be displayed</summary>

  `First number: -25, second number: 10`

  </summary>

---

## Exceptions

>"Computer says, no!"

- compilation errors & run-time errors
- *exception* - error in the program that occurs 
   during its execution and disrupts the normal
   flow of instructions. 
- *exception* is a shorthand for an exceptional event. 
- Examples: 
  - division by zero
  - trying to access an out-of-bounds array elements
  - trying to open a file that does not exists, etc. 

--- 

## Exception Handling

- Enable programs to catch and handle errors

- Used in situations when the system could recover from the malfunction causing the exception

- Exception handling is a recovery (from an error in the program) procedure 

- *Exception handler* is the code that executes when an exception has been detected.

---

## Exceptions in Kotlin 

- An exception  is represented by an object

- Various predefined classes for different exceptions that can occur during execution time

- Exceptions are *thrown* by a program, and may be caught and handled by another part of the program

- A program can be separated into a normal execution flow and an *exception execution flow*

---

## Kotlin Exception Handling 

1. A method detects an error.
 
2. The method *throws an exception*.

3. The exception is *caught* and *handled* by an exception handler. 


---
## Exception Hierachy

![bg right:65% w:850](https://images.ctfassets.net/em6l9zw4tzag/7J8MLkqvpL8Id0TfkMlf4K/c7c353a4ce33adde8507060344f6867f/android-exception-handling-Screenshot_2022-10-08_at_3.43.58_PM.png)

---

## Kotlin Exception Handling Example (1)

```kt
fun main(args: Array<String>) {
    val number1: Int; val number2: Int; val result: Int
    val firstNumber: String; val secondNumber: String
    firstNumber = JOptionPane.showInputDialog("Enter first integer")
    secondNumber = JOptionPane.showInputDialog("Enter second integer")
    number1 = firstNumber.toInt()
    number2 = secondNumber.toInt()
    result = number1 / number2
    JOptionPane.showMessageDialog(null, "The result is $result", "Result", JOptionPane.PLAIN_MESSAGE)
    System.exit(0)
}
```
---

## Kotlin Exception Handling Example (2)

```kt
fun main() {
    val number1: Int; val number2: Int; val result: Int
    val firstNumber: String; val secondNumber: String
    firstNumber = JOptionPane.showInputDialog("Enter first integer")
    secondNumber = JOptionPane.showInputDialog("Enter second integer")
    try {
        number1 = firstNumber.toInt()
        number2 = secondNumber.toInt()
        result = number1 / number2
        JOptionPane.showMessageDialog(
            null, "The result is $result",
            "Result", JOptionPane.PLAIN_MESSAGE
        )
    } catch (nfe: NumberFormatException) {
        JOptionPane.showMessageDialog(
            null,
            "You must enter two integers!", "Invalid Number Format", JOptionPane.ERROR_MESSAGE
        )
    } catch (ae: ArithmeticException) {
        JOptionPane.showMessageDialog(
            null,
            "Second number should not be zero!", "Division by zero",
            JOptionPane.ERROR_MESSAGE
        )
    }
    System.exit(0)
}
```

--- 

## Kotlin Exception Handling 

- *try block* - encloses the code that may generate an exception

- *catch blocks* - specify the type of exception it can catch and contains an exception handler, which contain code to process an exception

- *finally block* - provides code that always executes regardless of whether or not an exception occurs

- *throws clause* - throws the exception and lets the code run, sometimes with unexpected consequences.

---

![bg h:500 horizontal](../../figures/Error_Handling_1.svg)

![bg h:400 horizontal](../../figures/Error_Handling_2.svg)

---

## Try/catch blocks

```kt
try  {
     // code that might generate exceptions
}
catch ( ex1 : Exception )  {
	// handle exceptions of type Exception1
}
catch ( ex2 : Exception )  {
	// handle exceptions of type Exception1
}
catch ( ex3 : Exception )  {
	// handle exceptions of type Exception1
}…
finally { /*Optional*/

}
```

---
## Example Exceptions

- `IOException` - thrown when: 
  - not sufficient disk space to create a file 
  - a read-only file is opened for writing
  - an not existent file is opened for reading

- `NumberFormatException`
  - entering a non-numeric value for a numeric variable

- `ArithmeticException`
    - division by zero

---

## Handling Exceptions in Kotlin with `runCatching`

In Kotlin, the `runCatching` function provides a concise way to handle exceptions without the need for explicit `try-catch` blocks.

- In Kotlin, `runCatching` is a convenient utility that encapsulates a code block and allows you to handle exceptions in a more functional style.

- It is used to capture exceptions that might occur during the execution of a block of code.

---

## `runCatching` Syntax

```kotlin
val result = runCatching {
    // Code that may throw exceptions
    // ...
}

result.onSuccess { value ->
    // Code to handle the successful execution
    println("Result: $value")
}

result.onFailure { exception ->
    // Code to handle the exception
    println("Exception: $exception")
}
```
---
## Rethrowing Exceptions

```kotlin
val result = runCatching {
    // Code that may throw exceptions
    // ...
}

result.onFailure { exception ->
    when (exception) {
        is NumberFormatException -> {
            // Handle NumberFormatException
        }
        // Handle other specific exceptions
        else -> {
            // Handle any other type of exception
        }
    }
}
```
---

## Example of Slide 16 as `runCatching`

```kotlin
val resultCatching = runCatching {
    // Set Input fields with prompt.
    firstNumber = JOptionPane.showInputDialog("Enter first integer")
    secondNumber = JOptionPane.showInputDialog("Enter second integer")
    number1 = firstNumber.toInt()
    number2 = secondNumber.toInt()
    result = number1 / number2

    JOptionPane.showMessageDialog(null, "The result is $result", "Result", JOptionPane.PLAIN_MESSAGE)
}

// Handling NumberFormatException
resultCatching.onFailure { e ->
    when (e) {
        is NumberFormatException -> {
            JOptionPane.showMessageDialog(null, "You must enter two integers!", "Invalid Number Format", JOptionPane.ERROR_MESSAGE)
        }
        is ArithmeticException -> {
            JOptionPane.showMessageDialog(
                null,"Second number should not be zero!", "Division by zero", JOptionPane.ERROR_MESSAGE)
        }
        else -> throw e // rethrow other exceptions
    }
}
```
---

## `runCatching` vs `try`, `catch` and, `finally`

- **Functional Approach:** `runCatching` allows a more functional programming style for error handling, separating the success path from the error handling.

- **No Explicit try-catch:** There is no need for an explicit try-catch block. Instead, exceptions are handled using the `onFailure` and `getOrElse` functions.

- **Separation of Concerns:** Error handling is separated into specific blocks (`onFailure` and `getOrElse`), improving code readability and maintainability.

- **No Direct Equivalent of `finally`:** In this specific context, there is no direct equivalent of the `finally` block. Code outside the `runCatching` scope is used for logic that needs to run regardless of success or failure.

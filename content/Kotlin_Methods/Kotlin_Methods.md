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

    Course Code: ELEE1146 and COMP1836

    Course Name: Mobile Applications for Engineers/Technologists

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


## Function Declaration

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

## The `main()` function

- Every Kotlin application (Not Android) must contain a main method 

  ```kt
  fun main(args: Array<String>) {...}
  ```

- implicitly a `public` modifier which indicates that the `main` function can be called by any `object`. 

- `main()` is invoked when the the program it belongs to runs.
- `programName 1 2 3 4`
---
## How the `main()` function gets called?

- When the Kotlin interpreter executes an application it starts by calling the class `main` function

- The `main` method then calls all the other functions required to run your application

- The `main` method in the Kotlin language is similar to the main function in C, C++ and C# and many others.

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

![bg h:500 horizontal](../../figures/Java_Error_Handling_1.svg)
![bg h:400 horizontal](../../figures/Java_Error_Handling_2.svg)

---

## Try/catch blocks

```kt
try  {
     // code that might generate exceptions
}
catch ( Exception1 ex1 )  {
	// handle exceptions of type Exception1
}
catch ( Exception2 ex2 )  {
	// handle exceptions of type Exception1
}
catch ( Exception3 ex3 )  {
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
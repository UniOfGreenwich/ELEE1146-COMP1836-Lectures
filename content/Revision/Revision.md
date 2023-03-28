---
title: Revision
description: Revision
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

# Revision

    Course Code: ELEE1146 and COMP1836

    Course Name: Mobile Applications for Engineers/Technologists

    Credits: 15

    Module Leader: Seb Blair BEng(H) PGCAP MIET MIEEE MIHEEM FHEA

---

## Content for your exams

- Java
- Android architecture
- Programming concepts
- Development kits

---
## Java - Modifiers

- Access modifiers are a means of hiding the implementation details within a class
- Access modifiers specify levels of access control to and the visibility of class variables and methods
- Access modifier’s type:
  - `public` - can be accessed from everywhere
  - `private` - can only be accessed by the methods inside the class definition
  - `friendly` (default, no keyword) - can only be accessed by other classes in the same package
  - `protected` - can only be accessed by other classes in the same package or by subclasses of the class

---

## Java - Fields


Java field is declared using the following syntax:

```java
[access_modifier] [static] [final] type name [= initial value] ;
```

- `type` and `name` are mandatory
- `[]` are optional keywords

```java
public class Customer {
 // [access_modifier] [static] [final] type   name [= initial value]
    private            static  final  String field1 = "Fixed Value"; 
}
```

---

## Java - `Stringbuilder` 

- a **mutable** sequence of characters. 
- `String` Class in Java creates an **immutable** sequence of characters, 
- Constructs a string builder with no characters in it and an initial capacity of 16 characters

```java
StringBuilder str = new StringBuilder();

str.append("Hello");
str.append("World!");
// print string
System.out.println("String = " + str.toString());
```

<details>
<summary>Output?</summary>

```
String = HelloWorld!
```

</details>

<!--
modifying the `String` creates a new String object in the heap memory with the latest content, and the original String is never changed.
-->

---
 
## Java Classes

```java
// class Student definition
public class Student {
    private String name; 
    private int IDNumber;
    private String programme;
    private byte year;  

    // method declaration
    public double assessment( byte logBook, byte report, byte test, byte exam)
    {
        return ( 0.2 * logBook + 0.15 * report + 0.15 * test + 0.5 * exam );
    }                       
}
 ```

---

 Constructors are methods that initialise object instance variables

- They are invoked automatically each time an object of that class is instantiated

- The name of the constructor has to be the same as the class name (case sensitive)

- Constructors do not specify return values 

---

## Constructor Example

```java
public class BankCustomer  {
   private int accNumber, pin;
   private String firstName lastName;
   private double balance;
	// constructor   
	public BankCustomer ()  {
     setBankCustomer ( 0, 0,"","",0.0 );   
   }

    // set method
    public void setBankCustomer ( int acc, int p, Stirng fn,String ln, double bal ) { 
        accNumber = acc; pin = p;
        firstName = fn;  lastName = ln;
        balance = bal;                
    }
    
    public String toString( ) {
        return ( accNumber + “ “ + firstName + “ “ + lastName + “ £“ + balance );
    }
}	// class BankCustomer  

```  
--- 

## Java - Set/Get Methods

```java
public class Point  {
   private int x, y;
   public int getX(return this.x);
   public int getY(return this.Y);
   public void setX( int x1 ) { x = x1; }
   public void setY( int y1 ) { y = y1; }
   public void setPoint ( int x, int y ) {
      setX( x ); setY ( y );
   }
   public void printPointCoord ( ) {
	//some code here
    ...
   } 
}
```
---

## Andorid architecture - Kernel

- Linux kernel
- Type: Monolithic
![w:900 center](https://source.android.com/static/docs/core/architecture/images/generic-kernel-image-architecture.png)

---

## Andorid architecture - Processor Support
 
 ![w:800 center](https://www.esa-automation.com/wp-content/uploads/2017/05/ARM-x86.jpg)
  

---

## What is a Software Development Kit (SDK)?

- Is a collection of software development tools in one installable package.

- Can come with:
  - compiler
  - debugger
  - software framework
    - **inversion of control**- behavioural design,
    - **extensibility** - overriding, or adding specialised user code
    - **non-modifiable framework code** - user can extend the code, not modify the base

---

## APK vs SDK

- A **SDK** is typically a set of software development tools that allows the creation of applications for a certain software package, software framework, hardware platform, computer system, video game console, operating system, or similar development platform.

- **Android Package** is the package file format used by the Android operating system for distribution and installation of mobile apps and middleware

---

## SDK vs API

<p align="center">
  <img alt="Light" src="https://miro.medium.com/v2/resize:fit:720/0*7p6SKeXy_eDjh4uT" width="48%">
&nbsp; &nbsp; &nbsp; &nbsp;
  <img alt="Dark" src="https://miro.medium.com/v2/resize:fit:720/format:webp/1*bjQLLYpzN7VK8_6SxOHD0Q.jpeg" width="45%">
</p>

--- 
## Arrays [1]

- Definition
  - Arrays are data structures consisting of data items of the same type packaged together under one name.

- An array has:
  - elements have: 
    - positions (indices)  in the array

<div align=center>

|27|-7|0|16|38|40|16|77|16|
|--|--|--|--|--|--|--|--|--|
|c[0]|c[1]|c[2]|c[3]|c[4]|c[5]|c[6]|c[7]|c[8]|
</div>

`c[]` array elements, `c` array name

---

## Array [2]

- Declaration 
 `arrayType[ ] arrayName;` (`arrayName` is the identifier)
- Allocation - as an object
  - `arrayName = new arrayType[ arraySize ];` (`arraySize` is a  positive number)
- Initialisation
`arrayType[ ] arrayName  = {value1, value2, … , valueN };`
*`value1`, `value2`, … , `valueN` - list of values for array elements of `arrayType`

- Attribute 
`arrayName.length`

---

## Array [3]

Example 1:
```java
int[] c;        // declares the array
c = new int[8]; // allocates the memory
```


Example 2:
```java
// declares the array and allocates memory its elements
double[] b = new double[100];
String[] s = new String[5];
```

---

## Arrays [4]

- Combining declaration and initialisation - no `new` operator explicitly needed - `new` is invoked automatically

```java 
// declares and initialises - no allocation via new!
String daysOfTheWeek[] = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"};
```

- `arrayName.length` = the number of the elements in the array 
Example
```java
int length = daysOfTheWeek.length;  // int length = 7
```

---

## Arrays [5] - Initialisation

- In the declaration
  - Example:
```java
int[] a = {0,0,0,0,0,0}; 
int length = a.length; // is equal to 6
```

- one by one
  - Example:
```java
int[] a = new int[6]; 
a[0] = 0; a[1] = 0; a[2] = 0; [3] = 0; a[4] = 0; a[5] = 0; 
```

- Using a for loop
  - Example:
```java
int[] a = new int[6]; 
for (i = 0; i < a.length; i++ ) { a[i] = 0; }
```
---

## Arrays [6] - Examples

```java
{
    {
        int day = 5;
        String dayName;

        String dayOfTheWeek[] = {"Monday", "Tuesday", "Wednesday", 
                        "Thursday","Friday", "Saturday",  "Sunday" };
       
        if ( day > 7 || day < 1) 
        {
            dayName = "That is not a valid day of the week";
        }
        else
        {
             dayName = dayOfTheWeek[day-1]; // Saturday or Friday?
        }
    }
}
```

---
  
# Principle of Locality 

Programs tend to use data and instructions with addresses near or equal to those they have used recently​

​Temporal Locality: Recently referenced items are likely to be referenced again in the near future​

![center](../../figures/temp_local.png)

Spatial Locality: Items with nearby addresses tend to be referenced close together in time​

![center](../../figures/spatial_local.png)

---

## Locality Example

```c
int sum = 0;​
int a[5];
for ( int i = 0; i < n; i++ )​
{​
  sum += a[i];​
}
```

- Data
  - Access array elements `a[i]` in succession – Spatial Locality ​
  - Reference `sum` each iteration – Temporal Locality ​
- Instructions​
  - Reference instructions in sequence – Spatial Locality​
  - Cycle through loop repeatedly -  Temporal Locality​
  
---

## for-each Loop Sytnax

The syntax of the Java for-each loop is:
```java
for(dataType item : array) {
    ...
}
```

- array - an array or a collection
- item - each item of array/collection is assigned to this variable
- dataType - the data type of the array/collection
---


## for-each Loop Example 1: Print Array Elements
```java
// print array elements 
class Main {
  public static void main(String[] args) {
      
    // create an array
    int[] numbers = {3, 9, 5, -5};
    
    // for each loop 
    for (int number: numbers) {
      System.out.println(number);
    }
  }
}
```

---

## For loops and for each loops

```java
class Main {
 public static void main(String[] args) {
    
   char[] vowels = {'a', 'e', 'i', 'o', 'u'};

   // iterating through an array using a for loop
   for (int i = 0; i < vowels.length; ++ i) {
     System.out.println(vowels[i]);
   }
   // iterating through an array using the for-each loop
   for (char item: vowels) {
     System.out.println(item);
   }
 }
}
```
---

## Iniline `if`

- Java offers the ternary operator `?` `:` and it also reffered as conditional operator, inline if (iif), or ternary if.

- It allows the inline conditional execution exactly similar like `if...else...` statement but the `if...else...` statemnt is a **procedureal** statement but terniary operator `? :` is an inline function and it return a value of same data type.

```java
public static void main(String[] args) {
    int a = 3;
    int b = 6;

    String result = (a == b) ? "Both the numbers are equal" : "Both the numbers are NOT equal";
        
    System.out.println(result);
}
```

---

## Decisions - `switch`

```java
switch ( grade )
{ 
  case ‘A’ : System.out.println( “Excellent mark”);
     break;
  case ‘B’ : System.out.println( “Very good mark”)
     break;
  case ‘C’ : System.out.println( “Average mark”);
     break;
  case ‘D’ : System.out.println( “Below average mark”);
     break;
  default  : System.out.println(“Failing mark”);
     break;
}
```
---
## Decisions - `if` statements 
```java
char grade = ‘A’;

if ( grade == ‘A’) 
  System.out.println( “Excellent mark”);
else 
   if ( grade == ‘B’ ) 
     System.out.println( “Very good mark”);
   else
     if ( grade == ‘C’ )
       System.out.println( “Average mark”);
     else
       if ( grade == ‘D’ ) 
         System.out.println( “Below average mark”);
       else System.out.println(“Failing mark”);
```

---

## Good luck and have a good time in the exam!

![center](https://i.chzbgr.com/full/9029005056/h761B7854/photo-of-jake-gyllenhaal-situation-youre-in-when-taking-an-exam-and-see-the-first-question)
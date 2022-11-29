---
title: Java - Object Orientated Programmin
description: Java - Object Orientated Programmin
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

# Java - Object Orientated Programmin

    Course Code: ELEE1146 and COMP1836

    Course Name: Mobile Applications for Engineers/Technologists

    Credits: 15

    Module Leader: Seb Blair BEng(H) PGCAP MIET MIEEE MIHEEM FHEA

---

## OOP Key Concepts

- Classes and Objects

- Encapsulation

- Inheritance 

- Polymorphism

---

## Classes & Objects (1) 


> **Classes** are software programming models - abstractions of the real world or system entities. 

- Classes have *state* and *behaviour*

- *Variables* are used to describe the state of the class and methods are used to describe behaviour

- Classes are collections of objects with common structure, common behaviour, common relationships and common semantics

- Objects belong to a particular class, objects are instances of a particular class 

---

## Classes & Objects (2)

- **Class**
  - a template that describes the data and behaviour associated with instances of that class
  - the basic building block of an object-oriented language such as Java, C++, etc.
  - classes are data types and can be used to create multiple objects

- **Object**
  - represents something with which we can interact with in a program
  - an object’s behaviour defines a collection of services that we can tell it to perform for us
  - a class is abstract and represents a concept, and an object represents an instance (realization) of a class 

---

## Class - an Example

<div align=center>

![h:500](../../figures/java_class_diagram.svg)

</div>

---

## Class – an Example 2

<div align=center>

![h:500](../../figures/java_class_diagram_2.svg)

</div>


---

## Encapsulation (1)

- Any changes to the object's state (i.e. its variables) should be made only via that object's methods

- We should make it difficult, if not impossible, to access an object’s variables other than via its methods

- The user can request the object’s services, but s/he should not have to be aware of how those services are implemented

---

## Encapsulation (2)

- Data and methods are tied together in classes in OOP, i.e. classes *encapsulate* data representation and behaviour

- The user can view an object as a black box - s/he is not interested in the implementation but in the *interfaces* to the object

- information hiding - implementation details are hidden within the classes using `private` keyword
  - Examples - car, TV set, domestic appliances

---

## Encapsulation (3)

Encapsulation principle means that we should add to the same class behavioral methods (drive, stop, etc.).

<div align=center>

![h:500](../../figures/java_class_diagram_3.svg)

</div>

---

## Access Modifiers

- Access modifiers are a means of hiding the implementation details within a class
- Access modifiers specify levels of access control to and the visibility of class variables and methods
- Access modifier’s type:
  - `public` - can be accessed from everywhere
  - `private` - can only be accessed by the methods inside the class definition
  - `friendly` (default, no keyword) - can only be accessed by other classes in the same package
  - `protected` - can only be accessed by other classes in the same package or by subclasses of the class

---

## Class - an Example in Java


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


```java
Student stud1; // object declaration
```

---

## First Java Application - an Example

```java 
// My first Java program
public class Hello {
    // main method declaration
	public static void main(String[] args) {
            System.out.println("Hello world!");
	}
}
```

- Java programs are classes
- Every Java program consists of at least one class definition 
- Normally contains one or more methods
- Always contain the main method definition!
- Each class definition is enclosed in braces `{`  and  `}`
- Each method definition is enclosed in braces `{`  and `}`

---

## Java Primitive Data Types 

- Identifiers are the words a programmer uses in a program
  - An identifier can be made up of letters, digits, the underscore character ( _ ), and the dollar sign
  - Identifiers cannot begin with a digit

- Java is case sensitive - `MyClass`, `myClass`, and `MYCLASS` are different identifiers
- Numbers
  - whole numbers (integers)	`23`, `-768`
  - real numbers			`23.5`, `-2.7e+9`
  - Characters 				`‘a’`, `‘+’`, `‘2’`
  - Boolean				       `true`, `false`

--- 

## Java Primitive Data Types (q)

- Java is a *strongly-typed* language

  - Each variable must be declared first

  - Strict rules for assignment of values

- Java primitive data types are portable

- Every piece of data in a Java program is an object except for variables of primitive data types

---

## Declaration & Assignment

- Declaration 
  - specifies the variable type
  - `typeName var[, var];`

- Assignment
  - a sequential statement
  - assigns or gives a value to a variable
    - `varName = value;`
    - the value MUST be of the same type as the variable

---

## Declaration & Assignment 2

```java
int x;	// Define an int with the identifier called x

x = 12;	// Assign the identifer  

/* 
* Compound Declaration/assignment 
* statement 
*/

float myBalance = 1250.00f;
char aChar;		// Define a char
aChar = '!';	//Assignment Note the use of ''
char aLetter = ‘A‘;

long l1 = 200l, l2 = 200, l3 = 200L;
float f1 = 1f;
float f2 = 1e-45f; 	//10 to the power
double d1 = 47e47d;
boolean flag = true;				
```

---

## Access to the Private Members of a Class

- The access and any changes to the private instance variables values are implemented via methods

- Methods:
  - *mutator methods* - to change the value of an instance variable - also called set methods
  - *accessor methods* (query methods) -  to obtain the value of private instance variable - also called get methods
  - *constructors* – a specific type of mutator methods used to give initial values to objects

---

## Example - Set Methods

```java
public class Point  {
   private int x, y;
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

## Constructors

- Constructors are methods that initialise object instance variables

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

## Constructors Overloading


```java
public class BankCustomer  {
   
   private int accNumber, pin;
   private String firstName lastName;
   private double balance;
   
   // first constructor
   public BankCustomer ()  {
     setBankCustomer ( 0, 0,"","",0.0 );   
   }
   
   // second constructor
   public BankCustomer ( int acc, int p, double bal )  {
      setBankCustomer( acc, p,"", "", bal );
   }

   // third constructor   
   public BankCustomer ( int acc, int p, String fn, String ln, double bal )  {
      setBankCustomer( acc, p, fn, ln, bal );
   }

   ...
}

```

---

## Constructor 

```java

public class BankCustomerTest 
{
    public static void main ( String args[]) {
        //declaration
        BankCustomer cust1, cust2, cust3; 
        // initialisation
        // using first constructor
        cust1 = new BankCustomer ( );
        // using second constructor
        cust2 = new BankCustomer (4567891, 2345, 2345.50 );
        // using third constructor
        cust3 = new BankCustomer (2345678, 1234, "Some", "Person", 134.00);

        system.out.println("\n\n\t\t\tInformation for :\n\n");  
        printBankCustomer ( 1, cust1 );
        printBankCustomer ( 2, cust2 );
        printBankCustomer ( 3, cust3 );
    } // end main

    public void printBankCustomer ( int number, BankCustomer cust)
    {
        System.out.println( number + cust.toString() );
    }
}
```

---

## Set Methods

```java
public class BankCustomer  {
   private int accNumber, pin;
   private String firstName lastName;
   private double balance;
   // 3 constructors // same as before
   public BankCustomer ()  
   { ... }
   ...
   public void setAccount ( int acc ) 
   {  accountNumber = acc;   }
   public void setPIN ( int p ) 
   {  pin = p;   }
   public void setName ( String fn, String ln ) 
   {  firstName = fn;lastName = ln;  }
   public void setBalance ( double bal ) {  balance = bal;   }
}
```
---

## Get Methods

```java
public class BankCustomer  {
   private int accNumber, pin;
   private String firstName lastName;
   private double balance;
   // 3 constructors // same as before
   public BankCustomer ()  
   { ... }
   ...
   // no getPIN method !!! 
   public int getAccount( )  { 
      return accountNumber;  
   }
   public String getFirstName( )  { 
     return firstName; 
   }     
   public String getLastName( )  { 
     return lastName; 
   }
   public double getBalance( )  { 
     return balance; 
   }     

```

---

## Inheritance (1)

- Reuse do not reinvent!

- By using existing software components to create new ones, we take advantage of all the effort that went into the design, implementation, and 

- testing of the existing software

- Inheritance is the main idea behind existing classes in Java libraries - use them and adapt them to your own needs


---

## Inheritance (2)

- Inheritance allows a software developer to derive a new class from an existing one

- The new class (also called the child) inherits characteristics of the parent, i.e. the child inherits the methods and data defined in the parent class

- The original class is called superclass (base class, parent) 

- The new class is called subclasses (derived class, child)

- To tailor a derived class, the programmer can add new variables or methods, or can modify the inherited ones

---

## Single & Multiple Inheritance 

- Depending on the number of the superclasses a subclass is derived from the inheritance could be:
  - single inheritance - a subclass is derived from just one superclass, i.e. a child class can have only one parent class or
  - multiple inheritance - a subclass is derived from more than one superclass, inheriting the members of all parents, i.e. a child class can have two or more parents classes 
    - Example: family tree

---

## Single Inheritance in Java

We are using the keyword extends in Java to implement single inheritance

Example	

```java
  //           SubClass      SuperClass            
  public class MyClass extends Applet {
     // ...some code...
   }
```

---

## Multiple Inheritance in Java


- No “classical” multiple inheritance of classes in Java, e.g. a class can not be derived from multiple classes

- A Java class can only inherit from one superclass – BUT from multiple interfaces
  
```java
public MyClass extends Applet implements ActionListener, ItemListener  {
     		// ...some code...
  }
```

---

## Polymorphism

- From Greek, means “many forms”

- Allows us to process objects of all existing classes in a hierarchy in an uniform manner

- The main idea behind polymorphism is to have just one interface and multiple methods 

- The concept of polymorphism  let us use same name for more than one different purpose

- Example: overloaded constructors – same name, different parameters
This approach can be applied to every other method!


---

## Polmorphism 2

```java
class Shapes {
  public void area() {
    System.out.println("The formula for area of ");
  }
}

class Triangle extends Shapes {
  public void area() {
    System.out.println("Triangle is ½ * base * height ");
  }
}

class Circle extends Shapes {
  public void area() {
    System.out.println("Circle is 3.14 * radius * radius ");
  }
}

class Main {
  public static void main(String[] args) {
    Shapes myShape = new Shapes();  // Create a Shapes object
    Shapes myTriangle = new Triangle();  // Create a Triangle object
    Shapes myCircle = new Circle();  // Create a Circle object
    myShape.area();
    myTriangle.area();
    myShape.area();
    myCircle.area();
  }
}
```


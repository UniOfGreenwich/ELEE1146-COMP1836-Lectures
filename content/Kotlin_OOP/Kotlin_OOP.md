---
title: Object Orientated Programming
description: Object Orientated Programming
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

# Object Orientated Programming

    Course Code: ELEE1146 and COMP1836

    Course Name: Mobile Applications for Engineers/Technologists

    Credits: 15

    Module Leader: Seb Blair BEng(H) PGCAP MIET MIEEE MIHEEM FHEA

---

## OOP Key Concepts

- Classes and Objects

- Functions and Methods

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
  - the basic building block of an object-oriented language such as C++, C#, Java, Kotlin etc.
  - classes are data types and can be used to create multiple objects

- **Object**
  - represents something with which we can interact with in a program
  - an object’s behaviour defines a collection of services that we can tell it to perform for us
  - a class is abstract and represents a concept, and an object represents an instance (realisation) of a class 

---

## Class - an Example

<div align=center>

![h:500](../../figures/class_diagram.svg)

</div>

---

## Class – an Example 2

<div align=center>

![h:500](../../figures/class_diagram_2.svg)

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

![h:500](../../figures/class_diagram_3.svg)

</div>

---

## Visibility Modifiers

- Access modifiers are a means of hiding the implementation details within a class
- Access modifiers specify levels of access control to and the visibility of class variables and methods
- Access modifier’s type:
  - `public` (default, no keyword) - can be accessed from everywhere (implicit)
  - `private` - can only be accessed by the methods/functions inside the class definition
  - `internal`  - can only be accessed by other classes in the same package
  - `protected` - can only be accessed by other classes in the same package or by subclasses of the class

---

## Class - Example


```kt
// class Student definition
class Student {
    private var name: String? = null  
    private var IDNumber: Int? = null
    private var programme : String? = null
    private var year : Byte? = 0

    // method declaration
    fun assessment( logBook: Byte, report : Byte, test : Byte, exam : Byte ) : Double
    {
        return ( 0.2 * logBook + 0.15 * report + 0.15 * test + 0.5 * exam )
    }                       
}
 ```


```kt
var student : Student() // object declaration
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

```kt
class Point  {
   private var x : Int? = null
   private var y : Int? = null  
   private fun setX( x1: Int) { this.x = x1 }
   private fun setY( y1: Int) { this.y = y1 }
   fun setPoint ( x: Int, y: Int ) {
      setX( x ); setY ( y );
   }
   fun printPointCoord () {
    print("x=${this.x}, y=${this.y}")
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

```kt
class BankCustomer  {
   private var accNumber : Int? = null; private var pin : Int? = null
   private var firstName : String? = null; private var lastName: String? = null
   private var balance : Double? = null;
   // constructor   
   constuctor(){
     setBankCustomer ( 0, 0,"","",0.0 );   
   }

    // set method
    private fun setBankCustomer ( acc: Int, p: Int, fn : String, ln : String, bal: Double ) { 
        this.accNumber = acc; this.pin = p;
        this.firstName = fn;  this.lastName = ln;
        this.balance = bal;                
    }
    
    fun toString( ) : String {
        return ( "$accNumber $firstName $lastName £$balance" );
    }
}
```

--- 

## Constructors Overloading

```kt
class BankCustomer  {
   private var accNumber : Int? = null; private var pin : Int? = null
   private var firstName : String? = null; private var lastName: String? = null
   private var balance : Double? = null;
   
   // constructor   
   constructor()  {
     setBankCustomer ( 0, 0,"","",0.0 );   
   }
   // second constructor
   constructor( acc: Int, p : Int, bal: Double )  {
      setBankCustomer( acc, p,"", "", bal );
   }
   // third constructor   
   constructor( acc : Int, p : Int, fn : String, ln : String, bal : Double )  {
      setBankCustomer( acc, p, fn, ln, bal );
   }
   ...
}
```

---

## Constructor 

```kt
class BankCustomerTest 
{
  fun main(args: Array<String>) {
    //declaration and initialisation
    var cust1 : BankCustomer = BankCustomer(12312124,1234,0.0)
    var cust2 : BankCustomer = BankCustomer(12318888,1104, "First","Last",1200.00)
    var cust3 : BankCustomer = BankCustomer()
    // initialisation

    println("Information for :\n\n");
    printBankCustomer (1, cust1 );
    printBankCustomer (2, cust2 );
    printBankCustomer (3, cust3 );
  }

  fun printBankCustomer(number: Int, cust: BankCustomer) {
      println("${number} ${cust.customerToString()}")
  }
}
```

---

## Set Methods

```kt
class BankCustomer  {
   private var accNumber : Int? = null; private var pin : Int? = null
   private var firstName : String? = null; private var lastName: String? = null
   private var balance : Double? = null;
   // 3 constructors // same as before
   public BankCustomer ()  
   { ... }
   ...
   fun setAccount ( acc : Int ) 
   {  this.accountNumber = acc;   }
   fun setPIN ( p: Int ) 
   {  this.pin = p;   }
   fun setName (fn : String, ln : String ) 
   {  this.firstName = fn; this.lastName = ln;  }
   fun setBalance ( bal : Double ) {  this.balance = bal;   }
}
```
---

## Get Methods

```kt
class BankCustomer {
   private var accNumber : Int? = null; private var pin : Int? = null
   private var firstName : String? = null; private var lastName: String? = null
   private var balance : Double? = null;
   // 3 constructors // same as before
   public BankCustomer ()  
   { ... }
   ...
   // no getPIN method !!! 
   fun getAccount(): Int  { 
      return this.accountNumber;  
   }
   fun getFirstName() : String  { 
     return this.firstName; 
   }     
   fun getLastName() : String  { 
     return this.lastName; 
   }
   fun getBalance() : Double  { 
     return this.balance; 
   }
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

## Single Inheritance in Kotlin

We are using the keyword extends in Kotlin to implement single inheritance

Example	

```kt
  //    SubClass  SuperClass            
  class MyClass : Applet() {
     // ...some code...
   }
```

---

## Multiple Inheritance in Kotlin

- No “classical” multiple inheritance of classes in Kotlin, e.g. a class can not be derived from multiple classes
 
```kt
MyClass : Applet(), ActionListener(), ItemListener()  {
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

```kt
open class Shapes {
  open fun area() {
    println("The formula for area of ")
  }
}

class Triangle : Shapes() {
   override fun area() {
    println("Triangle is ½ * base * height ");
  }
}

class Circle : Shapes() {
  override fun area() {
    println("Circle is 3.14 * radius * radius ");
  }
}

fun main(args: Array<String>) {
    val myShape = Shapes()  // Create a Shapes object
    val myTriangle =  Triangle()  // Create a Triangle object
    val myCircle = Circle()  // Create a Circle object
    myShape.area()
    myTriangle.area()
    myShape.area()
    myCircle.area()
}
```


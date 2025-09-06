###### Week 1
**Java:** Java is a high-level, object oriented programming language
**Object-Oriented:** instructions are grouped with the data they operate on

**Advantages of OO**
1. Reusability
2. Avoiding code duplication
3. Easy to maintain
4. Extendibility
5. Greater Security

**Disadvantages of OO**
1. Size of the program
2. More effort to design and code
3. Lower performance

**Object:** An _object_ is an instance of a class. Objects also have attributes and behaviors

**Class:** A class can be considered a template or pattern from which objects can be _instantiated_ (created).
A class defines the essential characteristics of all the objects belonging to that class. 

**State:** The _state_ of an object is the value of its attributes
	 
**Identity:** The _identity_ of an object distinguishes one object from another. 

"objects with different identities may or may not be from the same class and may or may not have different states." 

**Compiler** – A compiler translates the entire code as one process. If any errors are encountered, they are presented to the user at the end of the compilation process. This process is generally a batch process.  
     
**Interpreter** – An interpreter performs the action of translating by interpreting one instruction at a time, and executes that instruction immediately. However, if an error is encountered, the interpreter stops and displays the error to the end user immediately. This process is generally an interactive process.

**Different between Compiler and Interpreter**

- **Compiler:**  = batch
    Translates the **entire program** in one go **before** running it.  
    ➤ It **generates a complete executable file** (like `.exe`) which can be run independently.
    
- **Interpreter:**  =line by line
    Translates **one instruction at a time**, **during** execution.  
    ➤ It **does not produce a separate executable** — it runs the code line-by-line.

**Order of executing a program**
 First write the code; then compile it; then debug and fix any errors; and lastly, execute the compiled code

- Writing 
- Compiling
- Debugging
- Executing

**What do the .Java and .class files contain?**
The **.Java** file contains the *Java source code* and the **.class** file contains *bytecode*

**Bytecode**
The intermediary code produced after compilation is called bytecode.
After running the code 

`javac Trains.java`

**Variable**
A _variable_ is a "container" that is used by a program to store a value.

**The purpose of declaring a variable is to notify the computing system of:** (Identify & store in memory)
- How much memory will be needed to *store* any value that variable may take, and
- Assign an _identity_ to that variable so that it can be accessed later.

**_Declaring_** a variable means just *stating* its *data type* and giving it a name for memory allocation. 

***Defining*** a variable means assigning a value to that variable.

`int total; //declaration
`total = 10; //definition`

**_primitive types_ and _object types_.** 

Primitive types are predefined as part of the Java language and are not associated with any classes. 

- int 
- double 
- char 
- boolean 

Object types are those defined by classes

- ***String***: An object of the String class is used to store a sequence of characters.

**Statements:** A statement is an action or series of actions ending in a semi-colon

**Expression:** An expression is a series of variables, operators, and method calls that evaluates to a single value.

*This doesn't end in a semi-colon*

`int enrolment = 100;`
`enrolment + 57        // this expression will evaluate to 157`

###### Week 2

- _fields —_ variables that store the attribute values of objects belonging to that class.
    
- _constructors —_ special types of methods that are used to initialize the values of a newly created object.
    
- _methods —_ sets of instructions that are used to implement the behavior of an object. An object should have _accessor_ and _mutator_ methods for its fields, as well as a _display_ method. It can also have other methods to define any other actions that are relevant for that object.
  
``` cpp 
 public class Car {
    // ----- Fields -----
    private String brand;
    private String color;
    private int speed;

    // ----- Overloaded Constructor -----
    public Car(String brand, String color, int speed) {
        this.brand = brand;
        this.color = color;
        this.speed = speed;
    }
	//----- Non-parameterised Constructor ----
	public Car(){}

    // ----- Accessor Methods -----
    public String getBrand() {
        return brand;
    }

    public String getColor() {
        return color;
    }

    public int getSpeed() {
        return speed;
    }

    // ----- Mutator Methods -----
    public void setColor(String color) {
        this.color = color;
    }

    public void setSpeed(int speed) {
        this.speed = speed;
    }

    // ----- Display Method -----
    public void displayInfo() {
        System.out.println("Brand: " + brand);
        System.out.println("Color: " + color);
        System.out.println("Speed: " + speed + " km/h");
    }
}
```

**Methods:** Methods are used to implement the *behavior* of an object. They have a *return* type, in comparison to constructor

***Display*** method is used to display the state of a method
Accessor and Mutator methods are also known as *Getters* and *Setters*

Methods in a class are always arranged alphabetically. Constructors always appear first in increasing order of formal parameters.

`public Strategy()`
`public Strategy(String name)`
`public Strategy(String name, int teamSize)`
`public void display()`
`public String getName()`
`public int getTeamSize()`
`public void setName(String newName)`
`public void setTeamSize(int teamSize)`
`public void testStrategy()`

**Access Modifier:** *Access modifier* defines the visibility of a section of the code. This could include a field, constructor, or method.

- **public -** classes, methods or constructors declared public can be accessed from any other class. Within the same package.

- **private -** methods, variables, and constructors that are declared private can only be accessed within the ***declared class*** itself. Using the private modifier is the main way that an object _encapsulates_ itself and hides data from the outside world.    
    
- **protected -** This modifier allows for sections of the code to be accessible to other classes that use _inheritance_. So child classes will be able to access

**Packages:** grouping *classes* together

**Constructors**: 
- Used to initialize the attributes of a class and create objects. 
- They should have the same name as the class name. 
- They do not have a *return*
- They can be overloaded. 

```cpp
  `public` Car(String b, int s) {
        brand = b;
        speed = s;
    }
```

There's 2 different types of constructors, *parameterized* and *default*

`public Rectangle(int length, int width){`
	 `length =  length;`
	 `width = width;`
`}`
`public Rectangle(int length){`
	`lenght= length;`
	 `width = 0;`
`}`
The second example is correct, even though only one param was there, the second variable was defined in the constructor. 

**Method Overloading:** same name but different signature. Which means parameters are different or number of params are different. 

###### **Relational Operators**

`int age = 20;`

`age > 20        //false`
`age >= 20       //true`
`age < 20        //false`
`age <= 20       //true`
`age == 20       //true`
`age != 20       //false`

###### **Logical Operators**

`! not - returns the logical opposite of its operand`

`&& and - the result is true only if both operands are true`

`|| or - the result is false only if both operands are false`

###### **Compound assignment operators**

`+= compound addition`
`–= compound subtraction`
`*= compound multiplication`
`/= compound division`
`%= compound modulus`

###### **Increment / Decrement**

`a++` & `a--`

``` java
//a++
int a = 10
int b = a++ // b = a 
			// a = a + 1
b = 11

//a--
int a =10
int b = ++a // a = a + 1
			// b =a
b = 10
```

![[Pasted image 20250822134536.png]]

**Explicit type cast**
- When we *cast* in front of the number to change its type
	`(int)10.35`

**Implicit type cast**
- Automatically converts the type since we are adding extra digits, for ex .00
	`int x = 10
	`double y = x    // y = 10.0

**Selection Constructs**
`if/else`
```java
if (conditional expression)
else // consequent
else if // alternative
```

`switch case`
```java
switch (expression)
case 1:
case 2:
	break; // break if this condition is true
default: //optional default ans

```

**Conditional Operator**

```java
isStudent ? "Student" : "Not a student"
//condition ? true : false
```

##### **Scanner Class** 

```java
import java.util.Scanner;

public class Read
{
    public static void main(String[] args)
    {
        Scanner console = new Scanner(System.in); //new object
        System.out.println("Please enter your first name and last name");
        String fName = console.next(); //to capture the input
        String lName = console.nextLine(); //another way to capture
    }
}
```

##### **Iterations**
Java supports two main types of loops:

- ***Pre-test loops:*** because the loop condition is tested prior to execution of the loo
	    `for & while loops`

- ***Post-test loops***: because the loop condition is tested after execution of the loop instructions. If the condition is true, the loop will repeat. If the condition is false, the loop exits.
		`do-while loops`

`for`
```java
for (int i = 0; i < max; i++)
        {
            System.out.println((i + 1));
        }
```

`while`
```java
int i = 0;
        while (i < max)
        {
            System.out.println((i + 1));
            i++;
        }
```

`do-while`
```java
do
	{
	    System.out.println((i + 1));
	    i++;
    } while (i < max);
```

**Collection**: A collection in Java is a data structure used to store sets of the same type of object

##### Arrays
- An array is a special type of collection that can store a fixed number of items.

```java
 //initialisation
 Student[] students = new Student[3];

        // Fill array with Student objects
        students[0] = new Student("Alice", 20);
        students[1] = new Student("Bob", 22);
        students[2] = new Student("Charlie", 19);

//another way to initialise
	String[] daysOfWeek = {"Sunday", "Monday", "Tuesday", "Wednesday",
                                 "Thursday", "Friday", "Saturday"};
 

```

*null*—a reserved word in Java that is used to mean 'no object' when an object variable is not currently referring to a particular object

**Class diagram**
A class diagram shows a program's classes, the classes' attributes and methods, and the relationships between the classes.
![[Pasted image 20250822221552.png]]

Unified Modelling Language (UML) is used in software engineering as a modelling language.

**Object Diagram**
An object diagram shows the objects and their relationships at one moment in time during the execution of an application. It gives information about objects at runtime and presents the dynamic view of a program.

![[Pasted image 20250822221541.png]]


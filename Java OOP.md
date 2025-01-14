### What is Java?
Java is called a **truly object oriented programming** language. Since, no statement in Java can be initialised without the `main` method (*functions in Java are called methods*). Hence, Java is more secure as an OOP language than C++ (which is called a partially *object oriented programming language*).

##### Invention of Java
Java was created by **James Gosling** in the year 1995 at Sun Microsystems. It was originally named "**Oak**". It has a logo of a coffee cup, with hot coffee.

#### Some overview on Java
- Java is OS independent. A java program can be run on any OS, irrespective of which OS it was originally created in.
- Whereas a Java program cannot be run without the `main` method, net-based Java program (called an **applet**), that doesn't have a `main` method. But an applet program ALWAYS have can be executed in a Java-enabled web browser only.

### Simple Java programs
```java
class Program {
	public static void main(String args[]) { // String is both a datatype and a class, so it is capital.
		System.out.println("Hello World");
	}
}
```
**How to run the file?** 
- The program name has to saved as `File_name.java`. 
- In the terminal, use `javac File_name.java` to compile the program.
- A new program called `File_name.class` is created in the directory, if compiled successfully.
- Then in the terminal write `java File_name` without any extensions. If the program is written correctly the output will be shown as "*Hello World*".

#### Anatomy of the Program
- Defined a class named `Program`. In Java, a class is always defined with a Capital starting letter.
- `public static void main(System args[])`: The `main` method of the program.
	- Here, `String` acts both like a datatype and a class. 
	- `public`: This method can be accessed from anywhere.
	- `static`: This means we don't need to create an object of the class to use this method.
	- `void`: This means the method does not return any value.
	- **Explaining the `(String[] args)`:**
		- `String[]` is an array of *String* objects.
		- `args` is just the name of the Array variable. 
		- `String[] args` lets the program to accept **Command line functions**, i.e. input provided when the program starts.
- `System.out.println("Hello");`: Here, the `System` is a class, whose object is `out` which is *static*. 
	- `System` is a built-in class in Java. It provides access to system resources, such as standard input, output, and error streams, as well as environment variables, system properties, and more. Inside `System`, there are various **static fields and methods**. One of those fields is `out`.
	- `out` is a static field in `System` class, and it is an object of the `PrintStream` class, which is another built-in class in Java. It is *static* since it belongs to the class `System` and not to any instance of it. 
	- `println` is the method of the `PrintStream` class that is used to print messages and to move to a new line.

#### Command Line Arguments
**Command-line arguments** in Java are inputs passed to the program when it is executed via the command line or terminal. They allow users to provide information or data to the program during runtime without requiring user input during program execution.

##### How to use them?
1. **Stored in the `String[] args`**: The `args` array holds the command-line arguments as strings.

2. **Passed During Execution:** Command-line arguments are passed after the program has been compiled, after the program name in the terminal, separated by spaces. `java Program args1 arg2 arg3`

3. **Accessed via indexing**: The arguments may be accessed using array indices. Usage: `args[0], args[1], args[2], ...`

4. **Count of arguments:** The length of the `args` array tells how many arguments the programmer has passed. Usage: `args.length`

##### Example Program
```java
public class AddNumbers {
    public static void main(String[] args) {
        if (args.length >= 2) {
            int num1 = Integer.parseInt(args[0]);
            int num2 = Integer.parseInt(args[1]);
            System.out.println("Sum: " + (num1 + num2));
        } else {
            System.out.println("Please provide two numbers as arguments!");
        }
    }
}
```
###### Execution:
```bash
java AddNumbers 5 10
```
###### Output
```Bash
Sum: 15
```

#### Static and Non-Static Objects, Variables or Methods:
- ###### Static Objects (or Members):
	- **Definition:** Static objects (fields or methods) belong to the **class** rather than any specific object of the class.
	- **Shared:** There is only **one copy** of a static object shared among all instances of the class.
	- **Access:** Static objects can be accessed directly using the **class name**, without creating an instance of the class.
	- **Memory Location:** Stored in the **method area** of memory (shared for all instances of the class).
- ###### Non-Static Objects (or Members):
	- **Definition:** Non-static objects (fields or methods) are specific to an **instance of a class**.
	- **Separate Copies:** Each instance of the class has its own copy of non-static fields.
	- **Access:** Non-static objects can only be accessed by creating an **instance** of the class.
	- **Memory Location:** Stored in the **heap memory** as part of the object.
###### When to Use Static and Non-Static?
- **Static:** Use when a variable or method should be shared among all objects of the class (e.g., global counters, utility functions).
- **Non-Static:** Use when each object requires its own unique data or behaviour.

**Non-static methods** can call both static and non-static variables, but **static** methods can ONLY use static variables.

#### Creation of an Object of a Class (*Instantiation* of a Class)
**An object is an *instance* of a class.**

`A obj = new A();`
Here,
- `A` is the Class Name.
- `obj` is the Object Name.
- `new` is the Operator, and is solely responsible for the creation of the memory for the class.
- `A()` is the *default constructor*. Parameterised constructor can also be used. The memory created by the `new` operator is initialised by the constructor.

##### Write a Java program to add and multiply two numbers.
```java
public class AddMulti() {
	public static void main(String[] args) {
		A obj = new A();
		obj.getdata(10, 20);
		obj.Add();
		obj.Multi();
	}
}
class A {
	int a, b;
	void getdata(int x, int y) {
		a = x;
		b = y;
	}
	void Add() {
		System.out.println("Addition of 10 and 20 = " + (a+b));
	}
	void Multi() {
		System.out.println("Multiplication of 10 and 20 = " + (a*b));
	}
}
```
**EXPLANATION OF THE ABOVE PROGRAM**
- The program starts in the `main` method of the `AddMulti` class.
- An object of the `A` class is created: `A obj = new A();`.
- The `getdata` method is called to initialise `a` and `b` with the values 10 and 20.
- The `Add` method calculates and prints the sum of 10 and 20.
- The `Multi` method calculates and prints the product of 10 and 20.

**KEY CONCEPTS USED**
- *Class and Object*:
    - The class `A` defines the blueprint, while `obj` is the instance of that class.
- *Encapsulation*:
    - Data (`a` and `b`) and methods (`getdata`, `Add`, `Multi`) are encapsulated in the `A` class.
- *Method Invocation*:
    - Methods are called on the object `obj` to perform operations.
- *Re-usability*:
    - The class `A` can be reused in other programs to perform addition and multiplication.

#### What is a **Constructor**?
A special method 

#### How to write a program without the `main` method?
It is possible using the `static {}` block. A `static` block is used before the `main` method or object creation that is executed **once** when the class is loaded into the memory. After the program is compiled, after going through the `static` block, the program tries to find the `main` method.

So, in the program, it is possible to use the `static` block and exit the program as soon as the `static` block is executed. The program will compile itself, but there will be an error in the program, since the `main` method is not found.

```java
public class hello {
	static {
		System.out.println("Hello World");
		System.exit(0);
	}
}
```

#### Taking User Input
In Java, inputs can be taken from the user by the following ways:
1. **Using `BufferedReader` class:** A system defined class that is included in the `java.io` package in Java.
	- **How to use `BufferedReader` class?**
		- Import the `BufferedReader` and `InputStreamReader` class.
		- Create a `BufferedReader` object.
		- Since `readLine()` throws `IOException`:
			- Use a `try-catch` block to handle it, OR
			- Add `throws IOException` to the method signature.
		- Read input using `readLine()` method.
		- Process the input using methods like `Integer.parseInt()` or `Double.parseDouble()` (static methods).
		- Finally, close the reader using using `reader.close()` method.
```Java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.IOException;

public class BufferedReaderExample {
    public static void main(String[] args) throws IOException {
        // Step 1: Create BufferedReader object
        BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));

        // Step 2: Read input
        System.out.print("Enter your name: ");
        String name = reader.readLine(); // Reads input as String

        System.out.print("Enter your age: ");
        int age = Integer.parseInt(reader.readLine()); // Convert input to int

        System.out.print("Enter your GPA: ");
        double gpa = Double.parseDouble(reader.readLine()); // Convert input to double

        // Step 3: Print the processed input
        System.out.println("\nUser Details:");
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("GPA: " + gpa);

        // Step 4: Close the reader
        reader.close();
    }
}

```

2. **Using `Scanner` class:** Another system defined class that is included in the `java.util` package in Java.
	- **How to use `Scanner` class?**
		- Import the `Scanner` class (use `*` to import every method in `java.util` package).
		- Create a `Scanner` object, e.g. `sc`.
		- Use the appropriate method (e.g., `nextInt()`, `nextDouble()`, `nextLine()`) to read the input using `System.in` for console input.
		- Finally close the scanner using the `sc.close()` method [whatever object name was written in Scanner object].
```Java
import java.util.Scanner;
public class Scan {
	public static void main(String[] args) {
	Scanner sc = new Scanner(System.in); // created sc object
	
	System.out.println("Enter your name: ");
	String name = sc.nextLine(); // reads string input
	
	System.out.println("Enter your age: ");
	int age = sc.nextInt(); // reads integer input
	
	System.out.println("Enter your salary: ");
	double salary = sc.nextDouble(); // reads double input
	
	System.out.println("\nUser Details:");
	System.out.println("Name: " + name); 
	System.out.println("Age: " + age); 
	System.out.println("Salary: " + salary); 
	
	sc.close(); // to terminate the scanner
	}
}
```

##### Write a Java Program to find the area of a rectangular room using two different classes.
```Java
class Area {
	int length;
	int breadth;
	void getData(int x, int y) {
		length = x;
		breadth = y;
	}
	int rectArea() {
		return (length * breadth);
	}
}
public class Rectangle {
	public static void main(String[] args) {
		
		//method 1
		Area obj1 = new Area();
		obj1.getData(10, 20);
		int area = obj1.rectArea();
		System.out.println("Area1 = " + area);

		//method 2 (without using methods from Area class)
		Area obj2 = new Area();
		obj2.length = 20;
		obj2.breadth = 40;
		System.out.println("Area2 = " + (obj2.length * obj2.breadth));
	}
}
```

#### `this` Keyword
The **`this`** keyword in Java is a reference variable that refers to the **current object** of the class. It is an important feature in Java, particularly in object-oriented programming, as it allows methods and constructors to interact with the object that invoked them.

***Current Object**: The **current object** refers to the instance of a class on which a method or constructor is currently being invoked. In object-oriented programming, every time you create an object and call its methods, the object itself becomes the context, or the current object, for those method calls.*

##### Usage of `this` program
1. **Refer the current object's instance variables**
	- `this` is used to resolve naming conflicts between instance variables and method parameters or local variables with the same.
```java
class Person {
    String name;

    // Constructor with parameter same as instance variable
    Person(String name) {
        this.name = name; // 'this.name' refers to the instance variable
    }

    void display() {
        System.out.println("Name: " + this.name);
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person("Alice");
        person.display(); // Output: Name: Alice
    }
}
```

2. **Call Another Constructor in the Same Class**
	- Use `this()` to call another constructor of the same class.
```java
class Person {
    String name;
    int age;

    // Default constructor
    Person() {
        this("Unknown", 0); // Calls the parameterized constructor
    }

    // Parameterized constructor
    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person();
        person.display(); // Output: Name: Unknown, Age: 0
    }
}
```

3. **Pass the current object as Argument**
	- The `this` keyword can be passed as an argument to a method or constructor.
```java
class Person {
    void print(Person obj) {
        System.out.println("Method invoked with object: " + obj);
    }

    void call() {
        print(this); // Passing the current object
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person();
        person.call();
    }
}
```

4. **Return the Current Object**
	- It can be used to return the current object from the method
```java
class Person {
    Person getObject() {
        return this; // Returns the current object
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person();
        Person obj = person.getObject(); // Stores the current object
        System.out.println(obj); // Output: Memory address of the object
    }
}
```

5. **Invoke a method in the same class**
	- The `this` keyword can be used to explicitly call a method of the current class.
```java
class Person {
    void show() {
        System.out.println("Show method invoked");
    }

    void callShow() {
        this.show(); // Explicitly calling show()
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person();
        person.callShow(); // Output: Show method invoked
    }
}
```

##### Key points to remember about `this`
- **`this` is always a reference for the current object.**
- `this` can only be used on **non-static** methods or constructors since static methods do not operate on object instances.
- When used in constructors, `this` must be the first statement. 
 
#### `abstract` keyword in Java
The **`abstract`** keyword in Java is used to define classes and methods that are **incomplete** and are meant to be extended or implemented by other classes. It allows the user to establish a blueprint for classes, enforcing certain methods to be defined by any subclass.

When the user declares an **abstract class**, a plan is set up for what all the objects created from its subclasses will have in common. Subclasses then *"fill in the blanks"* to create specific types of objects.

##### Key points about `abstract` keyword:
1. **Abstract Classes**: 
	- An abstract class is a class which cannot be instantiated (i.e. objects cannot be created from it)
	- It is meant to be extended by other classes.
	- It may or may not contain `abstract` methods.
```java
abstract class ClassName {
    // Abstract methods (no body)
    abstract void methodName();
    
    // Concrete methods (with body)
    void concreteMethod() {
        System.out.println("This is a concrete method.");
    }
}
```

2. **Abstract Methods:**
	- An abstract method is a method that is declared without a body (i.e. no implementation.)
	- Subclasses must provide an implementation for all abstract methods of their superclass.
```java
abstract void methodName();
```

##### Example program using `abstract` keyword.
```java
// Abstract class
abstract class Shape {
    // Abstract method (no body)
    abstract void draw();

    // Concrete method (has body)
    void description() {
        System.out.println("This is a shape.");
    }
}

// Subclass implementing the abstract method
class Circle extends Shape {
    void draw() {
        System.out.println("Drawing a Circle");
    }
}

// Another subclass
class Square extends Shape {
    void draw() {
        System.out.println("Drawing a Square");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape shape1 = new Circle();
        shape1.draw(); // Output: Drawing a Circle

        Shape shape2 = new Square();
        shape2.draw(); // Output: Drawing a Square
    }
}
```

##### Key points to remember about `abstract` keyword
1. Objects cannot be created from an abstract class.
2. An abstract class can contain both `abstract` and `concrete` methods
3. Abstract methods must be *declared within* an abstract class.
4. Subclasses are required to implement all the abstract methods of the superclass, unless the subclass is also declared as `abstract`.
5. In the concept of inheritance, if a subclass does not implement all abstract methods, it must also be declared abstract.
6. **Interface** is an `abstract` class where every method is also `abstract`.
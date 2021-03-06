# Java

#### Language purpose/genesis
* Why was the language created?
  * Java was originally created for interactive television.
  * Java was originally called "Oak," then it changed to "Green" and finally ended up as "Java."
  * There were 5 goals for the language:
    1. It must be "simple, object-oriented, and familiar"
    2. It must be "robust and secure"
    3. It must be "architecture-neutral and portable"
    4. It must execute with "high performance"
    5. It must be "interpreted, threaded and dynamic"
* What problems was the language trying to address?
  * Java's bytecode strategy was meant to let programmers "write once, run anywhere." As a result, compiled Java code is platform-independent (as long as that system supports Java, via a JRE with a JVM).
* Is the language a reaction to a previous language or a replacement for another language?
  * Java took a lot of its syntax from C and C++, but was not meant to handle all of the low-level operations they could perform.
  * Unlike C and C++ however, ,Java compiles to bytecode that is meant to be run on a JVM. This way, any machine can run the program as long as it supports Java.
  * Java doesn't do low-level operations as well as C or C++, but the Java API allows it to do much higher-level things with ease.

#### Unique features of the language
* Does the language have any particularly unique features?
  * Java bytecode
  * Java API
  * Lambda expressions
  * Popular for client-server applications
  * Java applications and Java web applets
  * Garbage collection

#### Name spaces
* How are name spaces implemented?
  * Java implements name spaces by organizing objects within packages.
* How are name spaces used?
  * At the top of a class, the first line specifies what package the class belongs to. Packages also offer one way to handle access control. For example, to restrict code to package-only, use the default modifier.

#### Types
* What types does the language support?
  * There are 8 primitive data types: `byte`, `short`, `int`, `long`, `float`, `double`, `boolean`, `char`
* Are both reference and value types supported?
  * Yes. Primitive data types are passed by value (unless you send the address), and objects are passed by reference.
* Can new value types be created?
  * Yes. You can create enumerations and classes that include state information.

#### Classes
* Defining
  * Classes have state and behavior, in the form of instance variables and methods.
* Creating new instances
  * You create a new object with the `new` keyword.
* Constructing/initializing
  * Every class has a constructor. If you do not explicitly write a constructor, there is a default constructor that takes no arguments.
  * If you explicitly define a no-arg constructor, the default constructor disappears.
* Destructing/de-initializing
  * Java's garbage collector automatically destroys an object when there are no longer any references to it.

Defining a class:
  ```java
  public class Car {
      // Instance variables
      public String make;
      public String model;
      public int year;
      public int speed;

      // Constructor
      public Car(String make, String model, int year) {
          this.make = make;
          this.model = model;
          this.year = year;
          this.speed = 0;
      }

      // Method
      public void accelerate(int amount) {
          this.speed += amount;
      }

      // Method
      public void decelerate(int amount) {
          this.speed -= amount;
      }
  }
  ```

Instantiating a class:
  ```java
  Car car = new Car("Volvo", "s60", 2012);
  ```

Instance reference name in data type (class)

```java
// Constructor
public Car(String make, String model, int year) {
    this.make = make;
    this.model = model;
    this.year = year;
    this.speed = 0;
}
```

#### Properties
* One of the way Java encapsulates data is through the use of getters and setters. They aren't built in, but are easy to write:

  ```java
  public int getSpeed() {
      return this.speed;
  }

  public void setSpeed(int speed) {
      this.speed = speed;
  }
  ```

* This allows the programmer to execute code/error check before changing the value of a field:

    ```java
    public void setSpeed(int speed) {
        if (speed > 0) {
            this.speed = speed;
        }
    }
    ```

#### Interfaces / protocols
* What does the language support?
  * Java uses interfaces, which specify what method(s) the class must implement:
* What abilities does it have?
  * Interfaces define what behavior a class should implement.
  * Interfaces can have one method or many methods. Those that only have one method are typically referred to as "functional interfaces", which work hand in hand with lambda expressions.
* How is it used?
  * Interfaces are linked to classes via the `implements` keyword right after the name of the class:

      ```java
      public class Worker implements Runnable {
          public void run() {

          }
      }
      ```

#### Inheritance / extension
* In Java, *everything* is an object. It all fits in one massive hierarchy of objects, and the root of it all is the Object class.
* By extending another class, a class "inherits" its fields and methods. If you are creating a new class and there is already another class that has some of the same code you want, you can just extend that class and reuse the code. There are two advantages to this: first, you have to write less code yourself, and secondly, reuse of code is a good thing and makes it easier to debug your program.

#### Reflection
* What reflection abilities are supported?
  * Java includes a Reflection API which can be used to examine classes, their fields, their methods and their constructors.
* How is reflection used?
  * Reflection can be used for many things, including:
      * Creating instances of extensibility objects using their fully-qualified names
      * Designing visual development environments that offer help to the programmer based on knowledge of the code
      * Debugging code even with private members of classes

#### Memory management
* How is it handled?
  * All Java objects are stored on the heap.
  * This heap is divided into two areas (also called generations). The first is the nursery and second is called the old space. When the nursery becomes full, objects are moved to the old space, and when the old space becomes full, the objects are deleted.
* How does it work?
  * As stated above, objects first enter the nursery when they are instantiated. When the nursery becomes full, the objects are then moved to the old space. One caveat to this movement of objects data is an area called the keep area. Newly allocated objects are put into the keep area and are not garbage collected into the old space until the next round of objects are added to the nursery.  
* Garbage collection?
  * Yes, when objects are not referenced anymore (and the heap becomes full), they are garbage collected (their memory is freed).
* Automatic reference counting?
  * No, Java uses the generational approach (nursery and old space) instead of reference counting.

#### Comparisons of references and values
* How are values compared? (i.e. comparing two strings)
  * In Java objects have the method `.equals()` for comparisons:
  ```java
  public class ComparisonExample {

      public static void main(String[] args) {

          /*String comparison example (this works for any object)*/
          String s1 = "String 1";
          String s2 = "String 2";

          if(s1.equals(s2)) {
              //this will not execute
              System.out.println("String 1 and String 2 are equal");
          } else {
              //this will execute
              System.out.println("String 1 is not equal to string 2");
          }

          /*Value comparison example*/
          int i = 1;
          int j = 1;

          if(i == j) {
              //this will execute
              System.out.println("i and j are equal");
          } else {
              //this will not execute
              System.out.println("i and j are not equal");
          }
      }
  }
  ```

#### Null/nil references
* Which does the language use? (null/nil/etc)
  * Java uses the `null` keyword
* Does the language have features for handling null/nil references?

#### Errors and exception handling
* Exceptions in Java are handled by `try-catch` blocks:
```java
try {
    //try something they may cause an error
} catch(Exception ex) {
    //do something to fix the exception (i.e. quit gracefully)
}
```

#### Lambda expressions, closures, or functions as types
  * As of Java 8, lambda expressions are supported. An example of a lambda statement can be found int the "Functional Programming" section below. Also, Java supports closures as anonymous inner classes and also methods as types through reflection.
  ```java
  //Example of Closures (Anonymous Inner Classes)
  public class AnonymousClass {
      interface HelloWorld {
          public void helloWorld();
          public void hello(String place);
      }
      public void createHelloWorld() {
          HelloWorld hello = new HelloWorld() {
              String world = "world";
          public void helloWorld() {
              hello("world");
          }
          public void hello(String place) {
              world = place;
              System.out.println("Hello " + place);
          }
      };
    }
  }
  ```
  ```java
  //Reflection (method as a variable) example
  Method method = ExampleClass.class.getDeclaredMethod("Method" + TestVar);
  method.inovke();
  ```
  
#### Implementation of listeners and event handlers
* An example of an event handler in Java is the `ActionEvent` in JavaFX. It is passed to methods and invoked when a UI elemet is interacted with.
#### Singleton
* How is a singleton implemented? Singletons are declared in Java by creating a `private` constructor, and then providing a method to get an instance, but only if the class has not been created yet, ensuring that only one instance of the object is created.
* Can it be made thread-safe? Yes, many different methods exist to make singletons thread safe. These include: creating the singleton at class load time, and synchronizing the getting of the instance.
* Can the singleton instance be lazily instantiated? Yes, by following the pattern described above, you can lazily instantiate the singleton.

#### Procedural programming
* Does the language support procedural programming?
  * Java was designed to be fully object oriented. All objects extend from a base `Object` class. The only exception to this (and what some argue does not make Java a "pure" object oriented language) is the inclusion of primitive types (`int`, `char`, etc...) that are not objects. Besides that, Java is fully object oriented and not procedural.

#### Functional programming
* Does the language support functional programming?
  * As of Java 8, Java supports some features of functional programming, specifically Lambda Expressions. Although this does not mean Java is fully a functional programming language, lambdas bring important features of a functional language.
  * Here is an example using the functional `Runnable` interface and lambdas:
  ```java
  public class LambdaExample {

      public static void main(String[] args) {

          Runnable r = () -> System.out.println("Hello from a runnable in a lambda!");

          r.run(); //this will print the text above
      }
  }
  ```

#### Multithreading
* Threads or thread-like abilities
  * Java supports multi-threaded applications
  * Because of how Java is run (inside the JVM), it actually is multi-threaded by default (i.e. the JVM is one thread and your program is another).
* How is multitasking accomplished?
  * Java implements multitasking in two ways:
    1. Implement the `Runnable` interface:
      ```java
      class RunnableExample implements Runnable {

          public void run() {
              //do something in a thread
          }

          public static void main(String args[]) {
              new RunnableExample().start();
          }
      }
      ```
    2. Extend the `Thread` class:
      ```java
      class ThreadExample extends Thread {

          public void run() {
              //do something in a thread
          }

          public static void main(String args[]) {
              new ThreadExample().start();
          }
      }
      ```

#### Sources
https://en.wikipedia.org/wiki/Java_(programming_language)  
https://gkdigital.com/questions/324/what-s-the-point-of-backing-fields  
https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Properties.html  
https://docs.oracle.com/javase/tutorial/java/concepts/interface.html  
https://docs.oracle.com/javase/tutorial/java/IandI/subclasses.html  
https://docs.oracle.com/javase/tutorial/reflect/  
https://docs.oracle.com/javase/tutorial/essential/concurrency/runthread.html  
https://www.beyondjava.net/blog/java-8-functional-programming-language/  
http://stackoverflow.com/questions/34834700/object-oriented-programming-vs-procedural-programming
http://www.javacoffeebreak.com/articles/inside_java/insidejava-nov99.html
https://docs.oracle.com/javase/tutorial/java/javaOO/anonymousclasses.html
http://stackoverflow.com/questions/4138527/how-to-call-a-java-method-using-a-variable-name

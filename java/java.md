# Java


#### Sources  
https://en.wikipedia.org/wiki/Java_(programming_language)

* Language purpose/genesis
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
* Unique features of the language
  * Does the language have any particularly unique features?
    * Java bytecode
    * Java API
    * Lambda expressions
    * Popular for client-server applications
    * Java applications and Java web applets
    * Garbage collection
* Name spaces
  * How are name spaces implemented?
    * Java implements name spaces by organizing objects within packages.
  * How are name spaces used?
    * At the top of a class, the first line specifies what package the class belongs to. Packages also offer one way to handle access control. For example, to restrict code to package-only, use the default modifier.
* Types
    * What types does the language support?
    * Are both reference and value types supported?
    * Can new value types be created?
* Classes
  * Defining
  * Creating new instances
  * Constructing/initializing
  * Destructing/de-initializing
* Instance reference name in data type (class)
  * this?  self?
* Properties
  * Getters and setters...write your own or built in?
  * Backing variables?
  * Computed properties?
* Interfaces / protocols
  * What does the language support?
  * What abilities does it have?
  * How is it used?
* Inheritance / extension
* Reflection
  * What reflection abilities are supported?
  * How is reflection used?
* Memory management
  * How is it handled?
    * All Java objects are stored on the heap.
    * This heap is divided into two areas (also called generations). The first is the nursery and second is called the old space. When the nursery becomes full, objects are moved to the old space, and when the old space becomes full, the objects are deleted.
  * How does it work?
  * Garbage collection?
    * Yes, when objects are not referenced anymore (and the heap becomes full), they are garbage collected (their memory is freed).
  * Automatic reference counting?
* Comparisons of references and values
  * How are values compared? (i.e. comparing two strings)
* Null/nil references
  * Which does the language use? (null/nil/etc)
  * Does the language have features for handling null/nil references?
* Errors and exception handling
* Lambda expressions, closures, or functions as types
* Implementation of listeners and event handlers
* Singleton
  * How is a singleton implemented?
  * Can it be made thread-safe?
  * Can the singleton instance be lazily instantiated?
* Procedural programming
  * Does the language support procedural programming?
    * Java was designed to be fully object oriented. All objects extend from a base `Object` class. The only exception to this (and what some argue does not make Java a "pure" object oriented language) is the inclusion of primitive types (`int`, `char`, etc...) that are not objects. Besides that, Java is fully object oriented and not procedural.
* Functional programming
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
* Multithreading
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

  #### Jon's Sources
  https://docs.oracle.com/javase/tutorial/essential/concurrency/runthread.html
  https://www.beyondjava.net/blog/java-8-functional-programming-language/
  http://stackoverflow.com/questions/34834700/object-oriented-programming-vs-procedural-programming
  http://www.javacoffeebreak.com/articles/inside_java/insidejava-nov99.html
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
      3.
  * What problems was the language trying to address?
    * Java's bytecode strategy was meant to let programmers "write once, run anywhere." As a result, compiled Java code is platform-independent (as long as that system supports Java, via a JVM).
  * Is the language a reaction to a previous language or a replacement for another language?
* Unique features of the language
  * Does the language have any particularly unique features?
* Name spaces
  * How are name spaces implemented?
  * How are name spaces used?
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
  * How does it work?
  * Garbage collection?
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
* Functional programming
  * Does the language support functional programming?
    * Test
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

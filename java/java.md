# Java

#### Sources  
https://en.wikipedia.org/wiki/Java_(programming_language)

* Language purpose/genesis
  * Why was the language created?
    * Java was originally created for interactive television, but it was ahead of its time.
    * The first release (Java 1.0) came out in 1995 and featured a fair amount of security as well as network and file access restrictions.
    * Many web browsers added Java compatibility so it was possible to run Java applets within web pages.
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
    * Unlike C and C++ however, Java compiles to bytecode that is meant to be run on a JVM. This way, any machine can run the program as long as it supports Java.
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
    * Java implements namespaces by organizing objects within packages.
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
* Multithreading
  * Threads or thread-like abilities
  * How is multitasking accomplished?

# Python

#### Language purpose/genesis
* Why was the language created?
  * Python was invented in 1989 by Guido van Rossum as a project to keep himself busy over a holiday when his office was closed. According to Wikipedia, he wanted to appeal to "Unix/C hackers".
* What problems was the language trying to address?
  * Python was trying to address many different things. A very important design choice in Python is its simplicity. Rossum wanted a language that was clean and not complex. He wanted it to be fun for programmers.
* Is the language a reaction to a previous language or a replacement for another language?
 * No, Rossum just decided to create Python out of boredom.

#### Unique features of the language
* Does the language have any particularly unique features?
  * The first unique part of Python that a new user will notice is that there are no curly braces. Code blocks are denoted by indentation. This hits on Rossum's philosophy of a non-cluttered and easily readable language.

#### Name spaces
* How are name spaces implemented?
  * Name spaces are implemented as each module, function and package having its own "namespace".
* How are name spaces used?
  * Name spaces in Python are used mainly to determine variable scope within each section of code.

#### Types
* What types does the language support?
  * Python is a duck and strongly typed language. Duck typing is when the type of the variable is only checked at runtime, as opposed to being checked at compile time (NOTE: Python is not compiled, it is interpreted). Although you do not have to type variables upon their declaration, the language will not allow operations on variables that are not safe.
* Are both reference and value types supported?
  * Types are not passed by reference or value in Python. They are passed by assignment. This means when you call a function, a reference to the object (the reference is actually passed by value) is sent to a function. This has to do with how some objects are mutable while others are not.
* Can new value types be created?
  * Yes, through the creation of classes, you can create different types in Python.

#### Classes
* Defining
  * To define a new class in Python, do the following
  ```python
  class Test:
      def __init__(self):
          self.x = 5
          self.y = 2
  ```
* Creating new instances
  * In Python, if you want to create a new instance you do the following:
  ```python
  class Test:
      def __init__(self):
          self.x = 5
          self.y = 2
  test_function = Test(5, 2)
  print(test_function.x) #prints 5
  print(test_function.y) #prints 2
  ```
* Constructing/initializing
  * Python uses the `__init__()` function to construct an instance of a class
* Destructing/de-initializing
  * This is handled by the garbage collector, so no user action needs to be taken.

#### Instance reference name in data type (class)
* this?  self?
  * Python uses the `self` keyword to reference an instance

#### Properties
* Getters and setters...write your own or built in?
  * You should not use getters and setters in Python.
* Backing variables?
  * Python does not have backing variables.
* Computed properties?
  * If you need to compute numbers dynamically, Python provides the `@property` directive. It is used like this:
  ```python
  class Computed:
      @property
      def x(self):
          if self._x is None:
              x = 0
          return self.x
      @x.setter
      def x(set, value):
          if self._x is None:
              _ = 0
              self._x = x
  ```

#### Interfaces / protocols
* What does the language support?
  * Python supports many different protocols. These special protocol names are denoted by `__function_name__()` notation (called "magic methods"). Python also supports interfaces. They are much more flexible than interfaces in Java. You can choose what version of an interface you wish to use on the fly, where as in Java, the version is very important.
* What abilities does it have?
  * Interfaces have the ability to allow users to call methods you write, such as creating a package for a user to import. "Magic methods" have many abilities. I go further into this below.
* How is it used?
  * Python "magic methods" are used to do many things. They construct objects, create a string out of an object, and even hash the object.

#### Inheritance / extension
* In Python, inheritance follows this syntax:
```python
class ExtendedClass(ParentClassName):
    def __init__(self, x, y, z):
        ParentClassName.__init__(self, x, y) #inheriting from the parent class
        self.z = z
```

#### Reflection
* What reflection abilities are supported?
  * Python has the ability to use reflection to see what type, class, attributes, and methods the object possesses.
* How is reflection used?
  ```python
  #Using the type() method to check the type of the object
      type("Hello World") #type = str
      type(5) #type = int
      type(5.0) #type = float

  #Checking to see if an object is an instance of a certain class
      isinstance("Hello World", str) #isinstance = true
      isinstance(5, int) #isinstance = true
      isinstance(5.0, int) #isinstance = false, 5.0 is a float
  ```

#### Memory management
* How is it handled?
  * According to the Python documentation, all objects and data in a program are stored on a private heap managed by the Python interpreter.
* How does it work?
  * At a low level the Python memory manager interacts with the operating system to request and ensure there is enough memory. It then can allocate space for the requested object.
* Garbage collection?
  * Garbage collection is handled by an algorithm that utilizes reference counting to determine if an object should be freed.
* Automatic reference counting?
  * Yes, this is how Python knows if an object is no longer in use/being referenced.

#### Comparisons of references and values
* How are values compared? (i.e. comparing two strings)
  * In Python, you can use the `==` operator to determine if two things are equal (e.g. 2 strings).

#### Null/nil references
* Which does the language use? (null/nil/etc)
  * Python uses the `None` keyword. Actually, in Python, `None` is an object that represents a state of nothing.
* Does the language have features for handling null/nil references?
  * Yes, you can use the `is` keyword to determine if an object has a state of `None`

#### Errors and exception handling
* If a syntax error occurs, the python interpreter will alert you to its presence. It is also refered to as a parsing error.
* Exceptions are handled like this:
```python
while True:
    try:
        x = str(input("Please enter a string: "))
        break
    except ValueError:
        print("That's not a string")
```

#### Lambda expressions, closures, or functions as types
* Python supports all of the above. Examples are below:
```python
#Example of a lambda in python:
l = lambda x, y : x - y
l(4,2) #The result is 2
#Example of a closure in python, and setting a function as a variable type:
def closure_test(output):
    def output_test():
        print(output)
    return output_test #returning the nested function
closure = closure_test("Hello World")
closure() #Outputs: Hello World
```

* Implementation of listeners and event handlers
  * Listeners and event handlers are implemented using the `EventHandler` class
  ```python
  def eventTest(): #defining a function to be used in the event handler
      print("Event happened!")
  class TestClass(object):
      def __init__(self):
          self.event = EventHandler(self)   
  ```
  ```python
  #calling the event handler
  testObject = TestClass()
  testObject.event += eventTest
  testobject.event() #This prints: "Event happened!"
  ```
* Singleton
  * How is a singleton implemented?
    * There seem to be a few different ways in python to accomplish this. According to StackOverflow, a singleton is implemented using meta classes as follows:
    ```python
    class Logger(metaclass=Singleton):
        pass
    ```
  * Can it be made thread-safe?
    * There seems to be mixed information on if this is possible in Python. Many people argue that implementing singletons in python isn't pythonic and argue against their use.
  * Can the singleton instance be lazily instantiated?
    * The same StackOverflow post referenced using lazy instantiation to instantiate hardware modules, so yes they can be instantianted in this way.
* Procedural programming
  * Does the language support procedural programming?
    * Yes, it does. You can rely solely on functions you define, and then call a main function that calls all of the other functions you created.
* Functional programming
  * Does the language support functional programming?
    * Yes, python supports functional programming. Actually, python supports four different paradigms of programming: Functional, Imperative, Object-Oriented, and Procedural.
* Multithreading
  * Threads or thread-like abilities
  * How is multitasking accomplished?

#### Sources
https://en.wikipedia.org/wiki/Python_(programming_language)
http://stackoverflow.com/questions/3913217/what-are-python-namespaces-all-about
http://stackoverflow.com/questions/986006/how-do-i-pass-a-variable-by-reference
https://en.wikibooks.org/wiki/Python_Programming/Reflection
http://stackoverflow.com/questions/6760685/creating-a-singleton-in-python
https://blog.newrelic.com/2015/04/01/python-programming-styles/
https://docs.python.org/3/

# C++

#### Language purpose/genesis
* Why was the language created?
  * C++ was created in 1979 by Bjarne Stroustup at Bell Labs. He wanted it to be like C, but with features of a higher-level language. It started as "C with Classes" but then became C++. According to Wikipedia, Stroustup wanted to "enhance the C language  with Simula-like features".
* What problems was the language trying to address?
  * The main problem addressed by C++ was adding abstraction to C, while maintaining fast performance. This is achieved through C's ability to access hardware, while adding conveniences like objects.
* Is the language a reaction to a previous language or a replacement for another language?
  * C++ is a layer of abstraction on top of the C language. C++ can be considered a subset of C.

#### Unique features of the language
* Does the language have any particularly unique features?
  * Stronger typing than C
  * Larger standard library than C
  * Constructors and destructors
  * Limiting the scope of data
  * Friendship

#### Namespaces
* Namespaces are used to differentiate between functions, classes and variables that share the same name but belong to different libraries. There are two ways to work with namespaces.  

#1: Explicitly declare the namespace along with each reference to the library:

```c++
#include <iostream>

int main() {
    std::cout << "Method 1!";
}
```

#2: Reference the namespace at the top of the program

```c++
#include <iostream>

using namespace std;

int main() {
    cout << "Method 2!";
}
```

#### Types
* What types does the language support?
    * `unsigned char`, `char`, `char16_t`, `char32_t`, `wchar_t`, `unsigned short`, `short`, `unsigned int`, `int`, `unsigned long`, `long`, `unsigned long long`, `long long`, `float`, `double`, `long double`, `bool`, `void`, `decltype(nullptr)`
* Are both reference and value types supported?
    * Yes. Primitive data types are passed by value to functions, but can be passed by reference if their addresses are sent instead. Pointers can also be sent for objects, structs, etc.

    ```c++
    int main() {
        int a = 6;
        int b = 5;

        int sum = add(a, b);
        int diff = subtract(&a, &b);
    }

    // Pass by value
    int add(int a, int b) {
        return a + b;
    }

    // Pass by reference
    int subtract(int *a, int *b) {
        return a - b;
    }
    ```

* Can new value types be created?
    * Structs hold data elements known as *members*.

    ```c++
    struct shirt {
        char size;
        int price;
    };
    ```

    * Unions look similar to structs, but all of their members share the same space in memory. Modifying one of the members will affect all the other members.

    ```c++
    union shirt {
        char size;
        int price;
    };
    ```

    * Enumerated types (enums) are used to restrict the possible values for a field.

    ```c++
    enum coins {penny, nickel, dime, quarter};
        ```

#### Classes
* Classes can hold data and functions. Thus every instance of that class is called an *object*, and it has both state and behavior.
* Classes are defined with the `class` keyword:

```c++
class Car {
    string make;
    string model;
    int year;
    int speed;

    Car::Car(string make, string model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
        this.speed = 0;
    }

    public void Car::accelerate(int amount) {
        this.speed += amount;
    }

    public void Car::decelerate(int amount) {
        this.speed -= amount;
    }
}
```

* Classes are instantiated by calling the constructor, which initializes the fields:

```c++
int main() {
  Car car("Volvo", "s60", 2012);
}
```

* The destructor of an object is called when its lifespan (based on its scope) ends.

#### Properties
* Getters and setters are not built in, but offer one strategy to encapsulate data.

```c++
int getSpeed() {
    return this.speed;
}

void setSpeed(int amount) {
    this.speed = speed;
}
```

* Alternatively, classes and functions can be labeled with the `friend` keyword. This allows it to access the private and protected members of that class.

```c++
class Car {
    string make;
    string model;
    int year;
    int speed;

    friend void changeYear(int);
}

void changeYear(int newYear) {
    year = newYear;
}
```

* Backing variables?
  * Backing variables came about in C#.
* Computed properties?
  * C++ does not offer computed properties per se, but another solution is to use `std::map` to hash keys into values.

#### Interfaces / protocols
* What does the language support?
  * C++ implements interfaces as **abstract classes**. These classes cannot be instantiated, but rather serve as a declaration of what functions must be implemented.
* What abilities does it have?
  * Abstract classes are useful because it can declare what functions need to be present, but each implementing class can define those functions however they need to.
* How is it used?
  * Classes are made abstract by declaring at least one of its functions as a **pure virtual** function. You can do this by placing "= 0" in its declaration.

  ```c++
  class Box {
      private:
          double length;
          double width;
          double height;
      public:
          virtual double getVolume() = 0;
  };
  ```

#### Inheritance / extension
* Inheritance in C++ is very similar to Java. The subclass "inherits" the members from its superclass, but can then further specify what is unique for itself.
* This is done with a `:` instead of `extends`.

```c++
class Ford: public Car {

}
```

#### Reflection
* What reflection abilities are supported?
  * C++ does not natively support any reflection capabilities.
  * However, some of the same effects can be provided with special meta compilers or meta frameworks.

#### Memory management
* How is it handled?
  * C++ is backwards compatible with C functions such as `malloc` and `free`, but these are rarely used.
  * Instead, C++ offers `new` and `delete`, which allocate and deallocate heap memory.
* How does it work?
  * Unlike `malloc`, `new` is type-aware, meaning no casting is required. If you put `int *a = new int(4);`, the `int` type is understood.
* Garbage collection?
  * C++ has optional support for garbage collection. For example, Sun offers a C++ compiler that includes the libgc library.
  * Another popular tool for garbage collection is RAII, which stands for "Resource Acquisition Is Initialization".
    * The key idea behind RAII is that a resource is owned by an object, so that object's destructor will automatically destroy its resources at the appropriate time.
* Automatic reference counting?
  * C++ offers reference counting with the `std::shared_ptr` class.

#### Comparisons of references and values
* Primitive data types can be easily compared with the `==` operator:

```c++
if (x == 5) {
    // Do something
}
```

* Strings can be compared with the `std::string::compare()` function:

```c++
if (s1.compare(s2) == 0) {
    // Do something
}
```

#### Null/nil references
* C++ uses `NULL`
* It does not have exception handling for null pointers; instead it will lead to undefined behavior.

#### Errors and exception handling
* C++ offers a `std::exception` class which declares some objects to be thrown as exceptions.
* C++ also offers *try-catch* blocks which will catch exceptions that are thrown. There can be multiple catch blocks associated with a try block.

#### Lambda expressions, closures, or functions as types
* Lambda expressions can be used in C++. For example, a lambda expression can be passed as an argument to the `std::sort` function:

```c++
#include <algorithm>  
#include <cmath>  

void abssort(float* x, unsigned n) {  
    std::sort(x, x + n,  
        // Lambda expression begins  
        [](float a, float b) {  
        return (std::abs(a) < std::abs(b));  
        } // end of lambda expression  
    );  
}  
```

#### Implementation of listeners and event handlers
* C++ doesn't have native support for event handling, but there are a couple ways to get around this.
  1. Create a multithreaded application and have one thread perform a continuous loop while waiting for a certain event.
  2. Use a framework that provides them (such as SDL, Qt or GNOME)

#### Singleton
* How is a singleton implemented?
  * A singleton is implemented with a global pointer, which can be initialized to 0 or `NULL`. When that class is instantiated for the first time, that object is assigned to the global pointer. Any time after that, if an instance of that class attempts to be instantiated, a simple `if` statement checks if the global pointer is already initialized. If it is, we know the singleton has already been made, and another object will not be created.
* Can the singleton instance be lazily instantiated?
  * Yes, but it is not thread safe.

#### Procedural programming
* Does the language support procedural programming?
  * Yes. It is also backwards-compatible with C, so you could write an entire program procedurally as in C.

#### Functional programming
* Does the language support functional programming?
  * Yes. Functional features are introduced in the C++11 standard.
  * However, instead of treating functions as objects (like true functional programming), C++ renders lambdas as a class with an operate method:

  ```c++
  auto println = [](const char  *message){ std::cout << message << std::endl;};
  ```

#### Multithreading
* How is multitasking accomplished?
  * C++ does not offer native multithreading support. Instead, it relies entirely on the operating system to provide this feature.
  * One way to do this is to use POSIX Threads (PThreads) which provides an API that can be included in your program.

#### Sources
https://www.tutorialspoint.com/cplusplus/  
http://www.cplusplus.com/doc/tutorial/  
https://en.wikibooks.org/wiki/C%2B%2B_Programming/Memory_Management#Garbage_Collection_and_RAII  
https://msdn.microsoft.com/en-us/library/dd293608.aspx  
http://blog.madhukaraphatak.com/functional-programming-in-c++/  
https://www.ukessays.com/essays/english-language/the-unique-features-of-c-in-programming-english-language-essay.php

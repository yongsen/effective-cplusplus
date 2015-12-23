# Reading notes for the book "Effective C++"

## Introduction
  - Declaration
  - Definition
  - Initialization
    * Default constructor
    * Copy constructor
    * Copy assignment operator
      * Undefined  behavior
      * Interface
      * Client
      
      *STL: containers, iterators, algorithms, and related functionality*

## Chapter 1 Accustoming yourself to C++
  - Item1:  Vies C++ as a federation of languages.
    * C
    * Object-Oriented C++
    * Template C++
    * The STL
  - Item2: Prefer consts, enums, and inlines (compiler) to #defines (preprocessor).
    * Simple constants: prefer const objects or enums to #defines.
    * Function-like macros: prefer inline functions to #defines.
  - Item3: Use const whenever possible. *
  - Item4: Make sure that objects are initialized before they're used.
    * Manually initialize objects of built-in type.
    * In a constructor, prefer use of the member initialization list to assignment inside the body of the constructor. List data members in the initialization list in the same order they're declared in the class.

## Chapter 2 Constructors, Destructors, and Assignment Operators
  - Item5: Know what functions C++ silently writes and calls.
    * Compilers may implicitly generate a class’s default constructor, copy constructor, copy assignment operator, and destructor.
  - Item6: Explicitly disallow the use of compiler-generated functions you do not want.
    * Compilers may implicitly generate a class’s default constructor, copy constructor, copy assignment operator, and destructor.
  - Item7: Declare destructors virtual in polymorphic base classes.
    * Polymorphic base classes should declare virtual destructors. If a class has any virtual functions, it should have a virtual destructor.
    * Classes not designed to be base classes or not designed to be used polymorphically should not declare virtual destructors.
  - Item8: Prevent exceptions from leaving destructors. *
  - Item9: Never call virtual functions during construction or destruction.
    * Don’t call virtual functions during construction or destruction, be- cause such calls will never go to a more derived class than that of the currently executing constructor or destructor.
  - Item10: Have assignment operators return a reference to `*this`.
  - Item11: Handle assignment to self in `operator=`.
    * Make sure operator= is well-behaved when an object is assigned to itself.
    * Make sure that any function operating on more than one object be- haves correctly if two or more of the objects are the same.
  - Item12: Copy all parts of an object.
    * Copying functions should be sure to copy all of an object’s data members and all of its base class parts.
    * Don’t try to implement one of the copying functions in terms of the other. Instead, put common functionality in a third function that both call.

## Chapter 3 Resource Management
  - Itme13: Use objects to manage resources.
  - Item14: Think carefully about copying behavior in resource-managing classes.
  - Item15: Provide access to raw resources in resource-managing classes.
  - Item16: Use the same form in corresponding uses of `new` and `delete`.
  - Item17: Store `new`ed objects in smart pointers in standalone statements.
  
## Chapter 4 Designs and Declarations

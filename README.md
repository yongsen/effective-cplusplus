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
  - Item18: Make interfaces easy to use correctly and hard to use incorrectly.
  - Item19: Treat class design as type design.
  - Item20: Prefer pass-by-reference-to-`const` to pass-by-value.
    * The rule doesn’t apply to built-in types and STL iterator and func- tion object types. For them, pass-by-value is usually appropriate.
  - Item21: Don't try to return a reference when you must return an object.
    * Never return a pointer or reference to a local stack object, a refer- ence to a heap-allocated object, or a pointer or reference to a local static object if there is a chance that more than one such object will be needed.
  - Item22: Declare data members `private`.
  - Item23: Prefer non-member non-friend functions to member functions.
  - Item24: Declare non-member functions when type conversions should apply to all parameters.
  - Item25: Consider support for a non-throwing `swap`.
  
## Chapter 5 Implementations
  - Item26: Postpone variable definitions as long as possible.
  - Item27: Minimize casting.
  - Item28: Avoid returning "handles" to object internals.
    * Avoid returning handles (references, pointers, or iterators) to object internals. Not returning handles increases encapsulation, helps const member functions act const, and minimizes the creation of dangling handles.
  - Item29: Strive for exception-safe code. *
  - Item30: Understand the ins and outs of inlining.
    * Limit most inlining to small, frequently called functions.
  - Item31: Minimize compilation dependencies between files.
  
## Chapter 6 Inheritance and Object-Oriented Design
  - Item32: Make sure public inheritance models "is-a".
    * Everything that applies to base classes must also apply to derived classes, because every derived class object is a base class object.
  - Item33: Avoid hiding inherited names.
  - 

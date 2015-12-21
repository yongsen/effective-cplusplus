# effective-cplusplus
Reading notes for the book "Effective C++"

## Introduction
  - Declaration
  - Definition
  - Initialization
    * Default constructor
    * Copy constructor
    * Copy assignment operator
      ** Undefined  behavior
      ** Interface
      ** Client
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
  - Manually initialize objects of built-in type.
  - In a constructor, prefer use of the member initialization list to assignment inside the body of the constructor. List data members in the initialization list in the same order they're declared in the class.

## Chapter 2 Constructors, Destructors, and Assignment Operators
  - Item5: 

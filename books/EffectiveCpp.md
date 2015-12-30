# Effective C++
*50 Specific Ways to Improve Your Programs and Designs*. First edition.

By Scott Meyers

I owe a lot to Scott Meyers' writing. Studying this book was a huge boost to my career. There are many ways to get into trouble with C++. Bjarne Stroustrup discusses in the ISO C++ FAQ the difference between legal and *moral* code. *Effective C++* exposed me to how to write moral code. In doing so, *Effective C++* also gave me a glimpse into some of the lower level details of how C++ works. Ever since I got a taste for how C++ works under the hood, I have been eager to learn more.

The copyright date for this book is 1992, so there are bound to be some items that are out-of-date. I think a majority of the content is still relevant and helpful.

## Shifting from C to C++
### Item 1: Use `const` and `inline` instead of `#define`
### Item 2: Prefer `iostream.h` to `stdio.h`
### Item 3: Use `new` and `delete` instead of `malloc` and `free`
### Item 4: Prefer C++-style comments

## Memory Management
### Item 5: Use the same form in corresponding calls to `new` and `delete`
### Item 6: Call `delete` on pointer members in destructors
### Item 7: Check the return value of `new`
### Item 8: Adhere to convention when writing `new`
### Item 9: Avoid hiding the global `new`
### Item 10: Write `delete` if you write `new`

## Constructors, Destructors, and Assignment Operators
### Item 11: Define a copy constructor and an assignment operator for classes with dynamically allocated memory
### Item 12: Prefer initialization to assignment in constructors
### Item 13: List members in an initialization list in the order in which they are declared
### Item 14: Make destructors virtual in base classes
### Item 15: Have `operator=` return a reference to `*this`
### Item 16: Assign to all data members in `operator=`
### Item 17: Check for assignment to self in `operator=`

## Classes and Functions: Design and Declaration
### Item 18: Strive for class interfaces that are complete and minimal
### Item 19: Differentiate among member functions, global functions, and friend functions
### Item 20: Avoid data members in the public interface
### Item 21: Use `const` whenever possible
### Item 22: Pass and return objects by reference instead of by value
### Item 23: Don't try to return a reference when you must return an object
### Item 24: Choose carefully between function overloading and parameter defaulting
### Item 25: Avoid overloading on a pointer and a numerical type
### Item 26: Guard against potential ambiguity
### Item 27: Explicitly disallow use of implicitly generated member functions you don't want
### Item 28: Use structs to partition the global namespace

## Classes and Functions: Implementation
### Item 29: Avoid returning "handles" to internal data from `const` member functions
### Item 30: Avoid member functions that return pointers or references to members less accessible than themselves
### Item 31: Never return a reference to a local object or a derefenced pointer initialized by `new` within the function
### Item 32: Use enums for integral class constants
### Item 33: Use inlining judiciously
### Item 34: Minimize compilation dependencies between files

## Inheritance and Object-Oriented Design
### Item 35: Make sure public inheritance models "is-a"
### Item 36: Differentiate between inheritance of interface and inheritance of implementation
### Item 37: Never redefine an inherited nonvirtual function
### Item 38: Never redefine an inherited default parameter value
### Item 39: Avoid casts down the inheritance hierarchy
### Item 40: Model "has-a" or "is-implemented-in-terms-of" through layering
### Item 41: Use private inheritance judiciously
### Item 42: Differentiate between inheritance and templates
### Item 43: Use multiple inheritance judiciously
### Item 44: Say what you mean; understand what you're saying

## Miscellany
### Item 45: Know what functions C++ silently writes and calls
### Item 46: Prefer compile-time and link-time errors to runtime errors
### Item 47: Ensure that global objects are initialized before they're used
### Item 48: Pay attention to compiler warnings
### Item 49: Plan for coming language features
### Item 50: Read the ARM

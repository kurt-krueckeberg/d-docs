# Arrays and Slices

[Arrays](https://dlang.org/spec/arrays.html) explains that the following are arrays D:

1. Raw C-like pointers
2. Static C-like arrays. 
3. Dynamic arrays are a bult-in type ID D. 

## Static Arrays

Static arrays are value types. They are passed they are passed to functions by value and returned from functions by value.

## Dynaimc Arrays
 
Dynaimc arrays are a built-in type of the D language. They are implement in the comp[iler and not in a standard library (like `std::vector` in C++). They are bounds cheked. The member variable `ptr` points to the underlying data:
Comment: Associative arrays in D are also native types in D, as is the string type. See [D Builtin Rationale](https://dlang.org/articles/builtin.html) 

todo: insert example.

## Array Slices

A slice is subarray of an existing array. It is a view of all or part of the array, and they offer great convienece while also being efficient since they havew negligible runtime overhead since 
they do not hold a copy of any of the underlying array data. As [Origins of the D Programming Language](https://dl.acm.org/doi/pdf/10.1145/3386323) explains:

> To the D programmer, an array slice is no different than a dynamic array. They support the same operations, they each have ptr and length properties, and can be passed as an argument to any function that accepts dynamic arrays.
> The only difference is a semantic one: a slice is produced from an existing dynamic or static array. A slice shares the same backing memory store as its source array until an element is appended to the slice, in which case new
> memory is allocated and the contents of the original store are copied over. The similarity between dynamic arrays and slices has led to inconsistent usage of the two terms, with some users maintaining the distinction and others
> referring to both as slices.

Slices to raw a raise are bounds checked. todo: give example.

### Operator [] operator is Overloaded for Slices

In D the index operator is overloaded for slices. todo: Give examples.

## Introduction

## Tilde(~) Operator is the Catenation Operator for Dynamic Arrays

* It can only be used with dynamic arrays
* It cann add a single element to an array or
* catenate two array

Further examples...

## Further Informations on Arrays and Slices in D

* [Arrays](https://dlang.org/spec/arrays.html) from **D Lanaguage Reference**.
* [D Slices](https://dlang.org/articles/d-array-article.html).

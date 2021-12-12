# Arrays and Slices

The D language spec article on [arrays](https://dlang.org/spec/arrays.html) gives a thorough explanation of all features and aspects of arrays. All of the following are arrays in D:

1. Raw pointers
2. Static arrays. 
3. Dynamic arrays, which are a bult-in type in D 

 D [arrays](https://dlang.org/spec/arrays.html) 

## Raw pointers

As in C, raw pointers to allocated memory can be used, and they have the same sematically equivalent `[]` and `*` operators. Raw pointer styles arrays are not bounds check, but slices to them are. See the Slices section below. Raw pointers must point to `null` or to valid memory. 

## Static Arrays

D also has C-like stack-based static arrays that are value types. They are passed to functions by value and returned from functions by value.

## Dynaimc Arrays
 
Dynaimc arrays are a built-in type in D. Unlik, say, C++, dynamic arrays are implemented in the compiler and not in a standard library. They are bounds checked. The member variable `ptr` points to the underlying data:

TODO: provide examples here

Comment: Associative arrays also native types in D, as is the string type. See the article [D Builtin Rationale](https://dlang.org/articles/builtin.html) for details. 

## Implicit Conversions

TODO: Add this.

## Array Slices

A slice is subarray of an existing array. It is a view of a portion of an array (or the entire array). Slices offer great convienece while also being efficient since they have negligible runtime overhead. As [Origins of the D Programming Language](https://dl.acm.org/doi/pdf/10.1145/3386323) explains:

> To the D programmer, an array slice is no different than a dynamic array. They support the same operations, they each have ptr and length properties, and can be passed as an argument to any function that accepts dynamic arrays.
> The only difference is a semantic one: a slice is produced from an existing dynamic or static array. A slice shares the same backing memory store as its source array until an element is appended to the slice, in which case new
> memory is allocated and the contents of the original store are copied over. The similarity between dynamic arrays and slices has led to inconsistent usage of the two terms, with some users maintaining the distinction and others
> referring to both as slices.

Slices to raw pointers are bounds checked. 

TODO: give example.

### Operator [] operator is Overloaded for Slices

In D the index operator is overloaded for slices. 

TODO: Give examples.
TODO: provide linek to further explantaion

## Concatenation with the Tilde(~) Operator

* It can only be used with dynamic arrays
* It cann add a single element to an array or
* catenate two array

Further examples...

## Further Informations on Arrays and Slices in D

* [Arrays](https://dlang.org/spec/arrays.html) from **D Lanaguage Reference**.
* [D Slices](https://dlang.org/articles/d-array-article.html).


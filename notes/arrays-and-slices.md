# Arrays and Slices

The the D language spec throughly explains [D's arrays](https://dlang.org/spec/arrays.html). All of the following are arrays in D:

1. Raw pointers
2. Static arrays. 
3. Dynamic arrays, which are a bult-in type in D 
4. Associate arrays

## Raw pointers

Pointers to allocated memory behave identically to pointers in **C** and have the same bulit-in `[]`  and `*` operators. Raw pointer access is not bounds check, but slices to raw pointer are bound checked. See the Slices section below. D raw pointers must point to `null` or to valid memory. 

## Static Arrays

D stack-based arrays that are value types. They are passed to functions by value and returned from functions by value.

## Dynaimc Arrays
 
Dynaimc arrays are a built-in type in D unlike, say, C++ were dynamic arrays are implemented in the standard library `std::vector` class. They are automatically bounds checked. Some brief code snippets illustrate their features:

```d
auto p = new int[7]; // raw pointer 
p[2] = p[2] + 10;
p[6] = p[2] + 10;
++p[0];
int[] slice = p;       // slice will be bounds checked
foreach(x; slice) {  // Iterate the slice
  writeln("x = ", x);
} 
```

## Associative Arrays
 
Associative arrays also native types in D (as is the string type) as [D Builtin Rationale](https://dlang.org/articles/builtin.html) explains.

## Array Slices

A slice is subarray of an existing array. It is a view of a portion (and the portion can be the entire array) of an array. Slices offer great convienece while also being efficient since they have negligible runtime overhead. As [Origins of the D Programming Language](https://dl.acm.org/doi/pdf/10.1145/3386323) explains:

> To the D programmer, an array slice is no different than a dynamic array. They support the same operations, they each have ptr and length properties, and can be passed as an argument to any function that accepts dynamic arrays.
> The only difference is a semantic one: a slice is produced from an existing dynamic or static array. A slice shares the same backing memory store as its source array until an element is appended to the slice, in which case new
> memory is allocated and the contents of the original store are copied over. The similarity between dynamic arrays and slices has led to inconsistent usage of the two terms, with some users maintaining the distinction and others
> referring to both as slices.

Slices to raw pointers are bounds checked. 

### Operator [] is Overloaded for Slices

In D the index operator is overloaded for slices. 

TODO: Give examples of how it is overloaded with explanations of the code.
TODO: provide linek to further explantaion

### Slices can Create a new Array

give brief examples with comments.

TODO: Link to D Programming book examples

## Tilde(~) is the Concatenation Operator

* It can only be used with dynamic arrays
* It cann add a single element to an array or
* catenate two array

Further examples...

## Further Informations on Arrays and Slices in D

* [Arrays](https://dlang.org/spec/arrays.html) from **D Lanaguage Reference**.
* [D Slices](https://dlang.org/articles/d-array-article.html).


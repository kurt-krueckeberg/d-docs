# Arrays and Slices

Static arrays in D are built-int types like most language. But dynamic arrays in D are also built-in types. This is the opposite approach of C++ where the standard library implements the dynamic array class `std::vector`.

Slices of Arrays are also a built-in types. Slice are views of arrays that are offer great convienece while also being efficient since they havew negligible runtime overhead.

Comment: Associative arrays in D are also native types in D, as is the string type. See [D Builtin Rationale](https://dlang.org/articles/builtin.html) 

## Introduction

As [Origins of the D Programming Language](https://dl.acm.org/doi/pdf/10.1145/3386323) explains:

> To the D programmer, an array slice is no different than a dynamic array. They support the same operations, they each have ptr and length properties, and can be passed as an argument to any function that accepts dynamic arrays.
> The only difference is a semantic one: a slice is produced from an existing dynamic or static array. A slice shares the same backing memory store as its source array until an element is appended to the slice, in which case new
> memory is allocated and the contents of the original store are copied over. The similarity between dynamic arrays and slices has led to inconsistent usage of the two terms, with some users maintaining the distinction and others
> referring to both as slices. 

## Further Informations on Arrays and Slices in D

* [Arrays](https://dlang.org/spec/arrays.html) from **D Lanaguage Reference**.
* [D Slices](https://dlang.org/articles/d-array-article.html).

# Arrays and Slices

Not only static arrays but dynamic arrays in D are built-in types of the languague. This is unlike a language like C++ in which the dynamic array class `std::vector` is implemented in the standard lanaguage.
Associative arrays are also native types in D, as is the string type. See [D Builtin Rationale](https://dlang.org/articles/builtin.html) for 

## Introduction

As is explained in [Origins of the D Programming Language](https://dl.acm.org/doi/pdf/10.1145/3386323):

> To the D programmer, an array slice is no different than a dynamic array. They support the same operations, they each have ptr and length properties, and can be passed as an argument to any function that accepts dynamic arrays.
> The only difference is a semantic one: a slice is produced from an existing dynamic or static array. A slice shares the same backing memory store as its source array until an element is appended to the slice, in which case new
> memory is allocated and the contents of the original store are copied over. The similarity between dynamic arrays and slices has led to inconsistent usage of the two terms, with some users maintaining the distinction and others
> referring to both as slices. 

## Further Informations

* [Arrays](https://dlang.org/spec/arrays.html) from **D Lanaguage Reference**.
* [D Slices](https://dlang.org/articles/d-array-article.html).

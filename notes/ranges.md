# Ranges in D

## Useful Resources, Articles, etc on Ranges

### Andrei Alexandrescu's Original Article Introducing Ranges

Andrei Alexandrescu [invented ranges](https://www.informit.com/articles/printerfriendly/1407357) while implementing D's generic algorithms package. His article is included [here](on_iterators.md).

### Iterators and Ranges: Comparing C++ to D to Rust

* [Iterators and Ranges: Comparing C++ to D to Rust - Barry Revzin](https://www.youtube.com/watch?v=d3qY4dZ2r4w)

This is a useful abstraction, because it allows us to write algorithms that are independent of the concrete type of the data source: any concrete type that provides the above interface qualifies as an input range and can be used with any algorithm that expects an input range.

### Excellent Introductions

* [D Programming--Ranges](https://adglob.in/blog/d-programming-ranges/)
* Slides to [Iterators Must Go](https://www.accu.org/conf-docs/PDFs_2009/AndreiAlexandrescu_iterators-must-go.pdf)


## Sources of Information

### Basic Introducton to Ranges

* [Introduction to Ranges](https://youtu.be/A8Btr8TPJ8c) video
* [Tutorial on Ranges](http://ddili.org/ders/d.en/ranges.html) from **Programming in D** book.
* [More on Ranges](http://ddili.org/ders/d.en/ranges_more.html) also from **Programming in D** book.

### Other Sources

* [Ranges in Algorithms](https://tour.dlang.org/tour/en/gems/range-algorithms) discusses how the algorithms in std.algorithm use ranges.
* D Wiki article: [Component Programming  with Ranges](https://wiki.dlang.org/Component_programming_with_ranges)
* [Ranges](https://tour.dlang.org/tour/en/basics/ranges) explains how `foreach` uses ranges and the semantics of ranges.

## D Ranges Class

**input range** is any type that implements three primitives:

empty: tells us whether the data source has any data left to be retrieved.
front: returns the current data item.
popFront: tells the data source to produce the next data item.
This is a useful abstraction, because it allows us to write algorithms that are independent of the concrete type of the data source: any concrete type that provides the above interface qualifies as an input range and can be used with any algorithm that expects an input range.

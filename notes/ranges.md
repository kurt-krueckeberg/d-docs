# Ranges in D

Andrei Alexandrescu invented [ranges](https://www.informit.com/articles/printerfriendly/1407357) while implementing D's generic algorithms package.

> Though iterators are safe and sensible, their interface prevents definition of flexible, general, and efficient container-independent algorithms. For example, you can't reasonably expect to sort, organize as a binary heap, or even reverse a container
> by just using its Iterator. [To provide container-independent algorithms] C++ defines its own conceptual hierarchy of iterators...  However, STL iterators are marred by lack of safety, difficulty of usage, difficulty of definition, and a very close relationship to C++
> that limits adoption by other languages. I propose an API that combines the advantages of Iterator and STL, and I bring evidence that the proposed abstraction is sensible by implementing a superset of STL's algorithms in the D language's standard library.

empty: tells us whether the data source has any data left to be retrieved.
front: returns the current data item.
popFront: tells the data source to produce the next data item.

This is a useful abstraction, because it allows us to write algorithms that are independent of the concrete type of the data source: any concrete type that provides the above interface qualifies as an input range and can be used with any algorithm that expects an input range.
## Sources of Information

### Basic Introducton to Ranges

* [Introduction to Ranges](http://dconf.org/2015/talks/davis.html) video
* [Tutorial on Ranges](http://ddili.org/ders/d.en/ranges.html) from
* [More on Ranges](http://ddili.org/ders/d.en/ranges_more.html) also from  **Programming in D** book.

### Other Sours

* [Ranges Algorithms](https://tour.dlang.org/tour/en/gems/range-algorithms) discusses how the algorithms in std.algorithm use ranges.
* D Wiki article: [Component Programming  with Ranges](https://wiki.dlang.org/Component_programming_with_ranges)
* [Ranges](https://tour.dlang.org/tour/en/basics/ranges) explains how `foreach` uses ranges and the semantics of ranges.


**input range** is any type that implements three primitives:

empty: tells us whether the data source has any data left to be retrieved.
front: returns the current data item.
popFront: tells the data source to produce the next data item.
This is a useful abstraction, because it allows us to write algorithms that are independent of the concrete type of the data source: any concrete type that provides the above interface qualifies as an input range and can be used with any algorithm that expects an input range.

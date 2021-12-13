# Ranges in D

Andrei Alexandrescu [invented ranges](https://www.informit.com/articles/printerfriendly/1407357) while implementing D's generic algorithms package.

> Though iterators are safe and sensible, their interface prevents definition of flexible, general, and efficient container-independent algorithms. For example, you can't reasonably expect to sort, organize as a binary heap, or even reverse a container
> by just using its Iterator. [To provide container-independent algorithms] C++ defines its own conceptual hierarchy of iterators...  However, STL iterators are marred by lack of safety, difficulty of usage, difficulty of definition, and a very close relationship to C++
> that limits adoption by other languages. I propose an API that combines the advantages of Iterator and STL, and I bring evidence that the proposed abstraction is sensible by implementing a superset of STL's algorithms in the D language's standard library.

C++ iterators suffer from being modelled on pointers. C++ STL algorihtms need two iterators, one that "indicates one past the end" just like pointers. The GoF iterator only requires one iterator because it contains a member variable that indicates when iteration is done.
The GoF iterator didn't cover random bidriection or random access. C++ introduced interator "concepts" or  categories--read, writer, forward, bidirecitonal, random. But this didn't address orthogonal issues of (in the case of the STL) where the iterator is swappable, writable, etc.

Resume article above [here](https://www.informit.com/articles/article.aspx?p=1407357&seqNum=7).

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

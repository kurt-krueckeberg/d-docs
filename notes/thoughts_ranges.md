Dave Abraham showed examples of very useful iterators that cannot not be used with STL's genetic algorithms because the stl iterators must have a `T& operator*()`, and container access  has nothing to do with the traversal requirements .
This rules out using a lot of useful iterators like....

Andrei Alex.. writes:

In the STL, *iter must be a reference to T and may or may not allow updates, depending on whether T is a const type. Sometimes, changing the referenced value is not even an option, as the underlying data source may be a read-only container or even an input stream.

Abrahams et al. 6 draw on existing experience with the STL to propose an extension to it that separates traversal and access into orthogonal concepts. Their suggestion is to classify iterators additionally in a second hierarchy of categories. These new categories are orthogonal to the classic iterator categories in Figure 1.

In brief:

    Readable iterators: You can write: value = *iter.

    Writable iterators: You can write: *iter = value.

    Swappable iterators: You can write: iter_swap(iter1, iter2).

    lvalue iterators: You can write: address = &(*iter); that is, you can take the address at which the iterated element lies in memory

Figure 2 illustrates the relationships among these categories. Any of them can be combined with one classic category in Figure 1. For example, you could define and use a bidirectional swappable iterator.

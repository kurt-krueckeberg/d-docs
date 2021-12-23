
**TODO:*: Merge exceprts from abrahams (below) into the On\_iteratos.md article.

The GoF Iterator Pattern is not sufficient to handle all stl algorithms, therefore the STL introduced iterator categories. These categories, howveer, place requirements on the return type of the dereference operator.
Dave Abraham gave examples of very useful iterators that cannot not be used with STL's genetic algorithms because the stl iterators must have a `T& operator*()`.
This rules out using a lot of useful iterators like....

Andrei Alex.. writes:

In the STL, *iter must be a reference to T and may or may not allow updates, depending on whether T is a const type. Sometimes, changing the referenced value is not even an option, as the underlying data source may be a read-only container or even an input stream.

[Abrahams et al.](https://www.boost.org/doc/libs/1_40_0/libs/iterator/doc/new-iter-concepts.html)[^6] draw on existing experience with the STL to propose an extension to it that separates traversal and access into orthogonal concepts. Their suggestion
is to classify iterators additionally in a second hierarchy of categories. Dave Abrahams points out examples for this change:

> For example, vector<bool>::iterator is almost a random access iterator, but the return type is not bool& (see issue 96 and Herb Sutter's paper J16/99-0008 = WG21 N1185). Therefore, the iterators of vector<bool> only meet the requirements of input
> iterator and output iterator. This is so nonintuitive that the C++ standard contradicts itself on this point. In paragraph 23.2.4/1 it says that a vector is a sequence that supports random access iterators.

> Another difficult-to-categorize iterator is the transform iterator, an adaptor which applies a unary function object to the dereferenced value of the some underlying iterator (see transform_iterator). For unary functions such as times, the return type
> of `operator*` clearly needs to be the result type of the function object, **which is typically not a reference.** Because random access iterators are required to return lvalues from operator*, if you wrap int* with a transform iterator, you do not get
> a random access iterator a might be expected, but an input iterator.

He mentions that: In short, there are many useful iterators that do not fit into the current standard iterator categories. As a result, the following bad things happen:

    Iterators are often mis-categorized (because they are forced to be).
    Algorithm requirements are more strict than necessary, because they cannot separate the need for random access or bidirectional traversal from the need for a true reference return type.

In brief:

    Readable iterators: You can write: value = *iter.

    Writable iterators: You can write: *iter = value.

    Swappable iterators: You can write: iter_swap(iter1, iter2).

    lvalue iterators: You can write: address = &(*iter); that is, you can take the address at which the iterated element lies in memory

Figure 2 illustrates the relationships among these categories. Any of them can be combined with one classic category in Figure 1. For example, you could define and use a bidirectional swappable iterator.

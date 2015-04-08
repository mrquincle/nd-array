# What is this?

This is a single templated class for an N-dimensional array or "tensor". I have been using it in a probabilistic context (as a data structure for discrete joint distributions and discrete conditional distributions).

The implementation is quite straightforward and uses an internal vector as internal data structure. A "good implementation" would define probably some good external iterators over such data structure instead. To go from a "tabular" index to a "linear index" there are two functions defined:

* `get_linear_index`
* `get_tabular_index`

There are a bunch of convenience functions for 2D and 3D arrays.

One specific function is really useful in a probabilistic setting, namely:

    value_container * get(const tabular_index & index, dimension_type summarize)

It "summarizes" the values of an nd-array in a particular dimension. For example, for a 2D array (a matrix) it returns values column-wise or row-wise. Note that it doesn't actually "sum" the values, it only returns a column or row.

Note that an nd-array can become really large. See the function `size()`. It is a multiplication of all the cardinalities of all involved dimensions.

# Copyrights

* License: LGPLv3, MIT and/or Apache.

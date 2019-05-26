<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.sparse.reduce_max_sparse" />
<meta itemprop="path" content="Stable" />
</div>

# tf.sparse.reduce_max_sparse

### Aliases:

* `tf.sparse.reduce_max_sparse`
* `tf.sparse_reduce_max_sparse`

``` python
tf.sparse.reduce_max_sparse(
    sp_input,
    axis=None,
    keepdims=None,
    reduction_axes=None,
    keep_dims=None
)
```



Defined in [`tensorflow/python/ops/sparse_ops.py`](/code/stable/tensorflow/python/ops/sparse_ops.py).

Computes the max of elements across dimensions of a SparseTensor. (deprecated arguments)

SOME ARGUMENTS ARE DEPRECATED. They will be removed in a future version.
Instructions for updating:
keep_dims is deprecated, use keepdims instead

This Op takes a SparseTensor and is the sparse counterpart to
`tf.reduce_max()`.  In contrast to SparseReduceSum, this Op returns a
SparseTensor.

Note: A gradient is not defined for this function, so it can't be used
in training models that need gradient descent.

Reduces `sp_input` along the dimensions given in `reduction_axes`.  Unless
`keepdims` is true, the rank of the tensor is reduced by 1 for each entry in
`reduction_axes`. If `keepdims` is true, the reduced dimensions are retained
with length 1.

If `reduction_axes` has no entries, all dimensions are reduced, and a tensor
with a single element is returned.  Additionally, the axes can be negative,
which are interpreted according to the indexing rules in Python.

#### Args:

* <b>`sp_input`</b>: The SparseTensor to reduce. Should have numeric type.
* <b>`axis`</b>: The dimensions to reduce; list or scalar. If `None` (the
    default), reduces all dimensions.
* <b>`keepdims`</b>: If true, retain reduced dimensions with length 1.
* <b>`reduction_axes`</b>: Deprecated name of axis.
* <b>`keep_dims`</b>: Deprecated alias for `keepdims`.


#### Returns:

The reduced SparseTensor.
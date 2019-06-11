<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.serialize_many_sparse" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.serialize_many_sparse

Serialize `N`-minibatch `SparseTensor` into an `[N, 3]` `Tensor`.

### Aliases:

* `tf.compat.v1.io.serialize_many_sparse`
* `tf.compat.v1.serialize_many_sparse`

``` python
tf.compat.v1.serialize_many_sparse(
    sp_input,
    name=None,
    out_type=tf.dtypes.string
)
```



Defined in [`python/ops/sparse_ops.py`](/code/stable/tensorflow/python/ops/sparse_ops.py).

<!-- Placeholder for "Used in" -->

The `SparseTensor` must have rank `R` greater than 1, and the first dimension
is treated as the minibatch dimension.  Elements of the `SparseTensor`
must be sorted in increasing order of this first dimension.  The serialized
`SparseTensor` objects going into each row of the output `Tensor` will have
rank `R-1`.

The minibatch size `N` is extracted from `sparse_shape[0]`.

#### Args:


* <b>`sp_input`</b>: The input rank `R` `SparseTensor`.
* <b>`name`</b>: A name prefix for the returned tensors (optional).
* <b>`out_type`</b>: The `dtype` to use for serialization.


#### Returns:

A matrix (2-D `Tensor`) with `N` rows and `3` columns. Each column
represents serialized `SparseTensor`'s indices, values, and shape
(respectively).



#### Raises:


* <b>`TypeError`</b>: If `sp_input` is not a `SparseTensor`.
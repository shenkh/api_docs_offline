<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.sparse.expand_dims" />
<meta itemprop="path" content="Stable" />
</div>

# tf.sparse.expand_dims

Inserts a dimension of 1 into a tensor's shape.

### Aliases:

* `tf.compat.v1.sparse.expand_dims`
* `tf.compat.v2.sparse.expand_dims`
* `tf.sparse.expand_dims`

``` python
tf.sparse.expand_dims(
    sp_input,
    axis=None,
    name=None
)
```



Defined in [`python/ops/sparse_ops.py`](/code/stable/tensorflow/python/ops/sparse_ops.py).

<!-- Placeholder for "Used in" -->

Given a tensor `sp_input`, this operation inserts a dimension of 1 at the
dimension index `axis` of `sp_input`'s shape. The dimension index `axis`
starts at zero; if you specify a negative number for `axis` it is counted
backwards from the end.

#### Args:


* <b>`sp_input`</b>: A `SparseTensor`.
* <b>`axis`</b>: 0-D (scalar). Specifies the dimension index at which to expand the
  shape of `input`. Must be in the range `[-rank(sp_input) - 1,
  rank(sp_input)]`.
* <b>`name`</b>: The name of the output `SparseTensor`.


#### Returns:

A `SparseTensor` with the same data as `sp_input`, but its shape has an
additional dimension of size 1 added.

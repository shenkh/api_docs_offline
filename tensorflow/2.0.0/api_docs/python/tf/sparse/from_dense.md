<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.sparse.from_dense" />
<meta itemprop="path" content="Stable" />
</div>

# tf.sparse.from_dense

``` python
tf.sparse.from_dense(
    tensor,
    name=None
)
```



Defined in [`tensorflow/python/ops/sparse_ops.py`](/code/stable/tensorflow/python/ops/sparse_ops.py).

Converts a dense tensor into a sparse tensor.

Only elements not equal to zero will be present in the result. The resulting
`SparseTensor` has the same dtype and shape as the input.

#### Args:

* <b>`tensor`</b>: A dense `Tensor` to be converted to a `SparseTensor`.
* <b>`name`</b>: Optional name for the op.


#### Returns:

The `SparseTensor`.
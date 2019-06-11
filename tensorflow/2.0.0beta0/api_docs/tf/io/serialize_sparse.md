<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.serialize_sparse" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.serialize_sparse

Serialize a `SparseTensor` into a 3-vector (1-D `Tensor`) object.

### Aliases:

* `tf.compat.v2.io.serialize_sparse`
* `tf.io.serialize_sparse`

``` python
tf.io.serialize_sparse(
    sp_input,
    out_type=tf.dtypes.string,
    name=None
)
```



Defined in [`python/ops/sparse_ops.py`](/code/stable/tensorflow/python/ops/sparse_ops.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`sp_input`</b>: The input `SparseTensor`.
* <b>`out_type`</b>: The `dtype` to use for serialization.
* <b>`name`</b>: A name prefix for the returned tensors (optional).


#### Returns:

A 3-vector (1-D `Tensor`), with each column representing the serialized
`SparseTensor`'s indices, values, and shape (respectively).



#### Raises:


* <b>`TypeError`</b>: If `sp_input` is not a `SparseTensor`.
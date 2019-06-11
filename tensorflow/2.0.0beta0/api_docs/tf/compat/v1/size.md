<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.size" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.size

Returns the size of a tensor.

``` python
tf.compat.v1.size(
    input,
    name=None,
    out_type=tf.dtypes.int32
)
```



Defined in [`python/ops/array_ops.py`](/code/stable/tensorflow/python/ops/array_ops.py).

<!-- Placeholder for "Used in" -->

Returns a 0-D `Tensor` representing the number of elements in `input`
of type `out_type`. Defaults to tf.int32.

#### For example:



```python
t = tf.constant([[[1, 1, 1], [2, 2, 2]], [[3, 3, 3], [4, 4, 4]]])
tf.size(t)  # 12
```

#### Args:


* <b>`input`</b>: A `Tensor` or `SparseTensor`.
* <b>`name`</b>: A name for the operation (optional).
* <b>`out_type`</b>: (Optional) The specified non-quantized numeric output type of the
  operation. Defaults to <a href="../../../tf.md#int32"><code>tf.int32</code></a>.


#### Returns:

A `Tensor` of type `out_type`. Defaults to <a href="../../../tf.md#int32"><code>tf.int32</code></a>.




#### Numpy Compatibility
Equivalent to np.size()


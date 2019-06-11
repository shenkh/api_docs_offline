<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.to_double" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.to_double

Casts a tensor to type `float64`. (deprecated)

``` python
tf.compat.v1.to_double(
    x,
    name='ToDouble'
)
```



Defined in [`python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use <a href="../../../tf/dtypes/cast.md"><code>tf.cast</code></a> instead.

#### Args:


* <b>`x`</b>: A `Tensor` or `SparseTensor` or `IndexedSlices`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` or `IndexedSlices` with same shape as `x` with
type `float64`.



#### Raises:


* <b>`TypeError`</b>: If `x` cannot be cast to the `float64`.
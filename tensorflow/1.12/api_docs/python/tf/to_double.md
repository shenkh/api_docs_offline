<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.to_double" />
<meta itemprop="path" content="Stable" />
</div>

# tf.to_double

``` python
tf.to_double(
    x,
    name='ToDouble'
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

Casts a tensor to type `float64`.

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor` or `IndexedSlices`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` or `IndexedSlices` with same shape as `x` with
type `float64`.


#### Raises:

* <b>`TypeError`</b>: If `x` cannot be cast to the `float64`.
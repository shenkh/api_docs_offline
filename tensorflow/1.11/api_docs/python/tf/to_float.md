<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.to_float" />
<meta itemprop="path" content="Stable" />
</div>

# tf.to_float

``` python
tf.to_float(
    x,
    name='ToFloat'
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

Casts a tensor to type `float32`.

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor` or `IndexedSlices`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` or `IndexedSlices` with same shape as `x` with
type `float32`.


#### Raises:

* <b>`TypeError`</b>: If `x` cannot be cast to the `float32`.
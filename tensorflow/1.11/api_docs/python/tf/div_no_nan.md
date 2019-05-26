<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.div_no_nan" />
<meta itemprop="path" content="Stable" />
</div>

# tf.div_no_nan

``` python
tf.div_no_nan(
    x,
    y,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guide: [Math > Arithmetic Operators](../../../api_guides/python/math_ops.md#Arithmetic_Operators)

Computes an unsafe divide which returns 0 if the y is zero.

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`.
* <b>`y`</b>: A `Tensor` whose dtype is compatible with `x`.
* <b>`name`</b>: A name for the operation (optional).

#### Returns:

The element-wise value of the x divided by y.
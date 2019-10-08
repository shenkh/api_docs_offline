<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.multiply_no_nan" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.multiply_no_nan

``` python
tf.math.multiply_no_nan(
    x,
    y,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

Computes the product of x and y and returns 0 if the y is zero, even if x is NaN or infinite.

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`.
* <b>`y`</b>: A `Tensor` whose dtype is compatible with `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The element-wise value of the x times y.
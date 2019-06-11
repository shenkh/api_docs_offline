<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.squared_difference" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.squared_difference

Returns (x - y)(x - y) element-wise.

### Aliases:

* `tf.compat.v1.math.squared_difference`
* `tf.compat.v1.squared_difference`
* `tf.compat.v2.math.squared_difference`
* `tf.math.squared_difference`

``` python
tf.math.squared_difference(
    x,
    y,
    name=None
)
```



Defined in generated file: `python/ops/gen_math_ops.py`.

<!-- Placeholder for "Used in" -->

*NOTE*: `math.squared_difference` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.
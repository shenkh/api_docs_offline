<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.maximum" />
</div>

# tf.maximum

### Aliases:

* `tf.math.maximum`
* `tf.maximum`

``` python
tf.maximum(
    x,
    y,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

See the guide: [Math > Basic Math Functions](../../../api_guides/python/math_ops.md#Basic_Math_Functions)

Returns the max of x and y (i.e. x > y ? x : y) element-wise.

*NOTE*: `math.maximum` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.
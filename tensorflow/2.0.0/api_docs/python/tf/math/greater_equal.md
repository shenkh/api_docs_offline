<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.greater_equal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.greater_equal

### Aliases:

* `tf.RaggedTensor.__ge__`
* `tf.Tensor.__ge__`
* `tf.greater_equal`
* `tf.math.greater_equal`

``` python
tf.math.greater_equal(
    x,
    y,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Returns the truth value of (x >= y) element-wise.

*NOTE*: `math.greater_equal` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `uint8`, `int16`, `int8`, `int64`, `bfloat16`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.
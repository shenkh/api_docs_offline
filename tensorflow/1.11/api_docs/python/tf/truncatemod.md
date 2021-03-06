<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.truncatemod" />
<meta itemprop="path" content="Stable" />
</div>

# tf.truncatemod

``` python
tf.truncatemod(
    x,
    y,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

See the guides: [Math > Arithmetic Operators](../../../api_guides/python/math_ops.md#Arithmetic_Operators), [Upgrade to TensorFlow 1.0 > Upgrading your code manually](../../../api_guides/python/upgrade.md#Upgrading_your_code_manually)

Returns element-wise remainder of division. This emulates C semantics in that

the result here is consistent with a truncating divide. E.g. `truncate(x / y) *
y + truncate_mod(x, y) = x`.

*NOTE*: `TruncateMod` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`, `bfloat16`, `half`, `float32`, `float64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.
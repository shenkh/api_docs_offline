<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.floormod" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.floormod

Returns element-wise remainder of division. When `x < 0` xor `y < 0` is

### Aliases:

* `tf.RaggedTensor.__mod__`
* `tf.compat.v1.RaggedTensor.__mod__`
* `tf.compat.v1.floormod`
* `tf.compat.v1.math.floormod`
* `tf.compat.v1.math.mod`
* `tf.compat.v1.mod`
* `tf.compat.v2.RaggedTensor.__mod__`
* `tf.compat.v2.math.floormod`
* `tf.compat.v2.math.mod`
* `tf.math.floormod`
* `tf.math.mod`

``` python
tf.math.floormod(
    x,
    y,
    name=None
)
```



Defined in generated file: `python/ops/gen_math_ops.py`.

<!-- Placeholder for "Used in" -->

true, this follows Python semantics in that the result here is consistent
with a flooring divide. E.g. `floor(x / y) * y + mod(x, y) = x`.

*NOTE*: `math.floormod` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`, `bfloat16`, `half`, `float32`, `float64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

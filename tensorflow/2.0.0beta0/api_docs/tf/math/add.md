<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.add" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.add

Returns x + y element-wise.

### Aliases:

* `tf.RaggedTensor.__add__`
* `tf.add`
* `tf.compat.v1.RaggedTensor.__add__`
* `tf.compat.v1.add`
* `tf.compat.v1.math.add`
* `tf.compat.v2.RaggedTensor.__add__`
* `tf.compat.v2.add`
* `tf.compat.v2.math.add`
* `tf.math.add`

``` python
tf.math.add(
    x,
    y,
    name=None
)
```



Defined in generated file: `python/ops/gen_math_ops.py`.

<!-- Placeholder for "Used in" -->

*NOTE*: `math.add` supports broadcasting. `AddN` does not. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `uint8`, `int8`, `int16`, `int32`, `int64`, `complex64`, `complex128`, `string`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

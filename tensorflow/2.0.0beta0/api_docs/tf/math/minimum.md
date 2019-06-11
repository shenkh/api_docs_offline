<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.minimum" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.minimum

Returns the min of x and y (i.e. x < y ? x : y) element-wise.

### Aliases:

* `tf.compat.v1.math.minimum`
* `tf.compat.v1.minimum`
* `tf.compat.v2.math.minimum`
* `tf.compat.v2.minimum`
* `tf.math.minimum`
* `tf.minimum`

``` python
tf.math.minimum(
    x,
    y,
    name=None
)
```



Defined in generated file: `python/ops/gen_math_ops.py`.

<!-- Placeholder for "Used in" -->

*NOTE*: `math.minimum` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

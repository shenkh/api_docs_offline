<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.expm1" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.expm1

### Aliases:

* `tf.expm1`
* `tf.math.expm1`

``` python
tf.math.expm1(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

See the guide: [Math > Basic Math Functions](../../../../api_guides/python/math_ops.md#Basic_Math_Functions)

Computes exponential of x - 1 element-wise.

I.e., \\(y = (\exp x) - 1\\).

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.
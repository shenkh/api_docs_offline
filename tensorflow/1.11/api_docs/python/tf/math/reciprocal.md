<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.reciprocal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.reciprocal

### Aliases:

* `tf.math.reciprocal`
* `tf.reciprocal`

``` python
tf.math.reciprocal(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

See the guides: [Math > Basic Math Functions](../../../../api_guides/python/math_ops.md#Basic_Math_Functions), [Upgrade to TensorFlow 1.0 > Upgrading your code manually](../../../../api_guides/python/upgrade.md#Upgrading_your_code_manually)

Computes the reciprocal of x element-wise.

I.e., \\(y = 1 / x\\).

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.
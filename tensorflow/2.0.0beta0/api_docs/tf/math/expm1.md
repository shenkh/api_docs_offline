<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.expm1" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.expm1

Computes exponential of x - 1 element-wise.

### Aliases:

* `tf.compat.v1.expm1`
* `tf.compat.v1.math.expm1`
* `tf.compat.v2.math.expm1`
* `tf.math.expm1`

``` python
tf.math.expm1(
    x,
    name=None
)
```



Defined in generated file: `python/ops/gen_math_ops.py`.

<!-- Placeholder for "Used in" -->

I.e., \\(y = (\exp x) - 1\\).

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

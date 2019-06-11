<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.rsqrt" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.rsqrt

Computes reciprocal of square root of x element-wise.

### Aliases:

* `tf.compat.v1.math.rsqrt`
* `tf.compat.v1.rsqrt`
* `tf.compat.v2.math.rsqrt`
* `tf.math.rsqrt`

``` python
tf.math.rsqrt(
    x,
    name=None
)
```



Defined in generated file: `python/ops/gen_math_ops.py`.

<!-- Placeholder for "Used in" -->

I.e., \\(y = 1 / \sqrt{x}\\).

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

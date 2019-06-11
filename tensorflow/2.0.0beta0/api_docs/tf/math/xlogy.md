<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.xlogy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.xlogy

Returns 0 if x == 0, and x * log(y) otherwise, elementwise.

### Aliases:

* `tf.compat.v1.math.xlogy`
* `tf.compat.v2.math.xlogy`
* `tf.math.xlogy`

``` python
tf.math.xlogy(
    x,
    y,
    name=None
)
```



Defined in generated file: `python/ops/gen_math_ops.py`.

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

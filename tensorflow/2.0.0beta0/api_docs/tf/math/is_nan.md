<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.is_nan" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.is_nan

Returns which elements of x are NaN.

### Aliases:

* `tf.compat.v1.debugging.is_nan`
* `tf.compat.v1.is_nan`
* `tf.compat.v1.math.is_nan`
* `tf.compat.v2.math.is_nan`
* `tf.math.is_nan`

``` python
tf.math.is_nan(
    x,
    name=None
)
```



Defined in generated file: `python/ops/gen_math_ops.py`.

<!-- Placeholder for "Used in" -->



#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


#### Numpy Compatibility
Equivalent to np.isnan


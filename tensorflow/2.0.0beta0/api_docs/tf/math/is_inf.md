<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.is_inf" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.is_inf

Returns which elements of x are Inf.

### Aliases:

* `tf.compat.v1.debugging.is_inf`
* `tf.compat.v1.is_inf`
* `tf.compat.v1.math.is_inf`
* `tf.compat.v2.math.is_inf`
* `tf.math.is_inf`

``` python
tf.math.is_inf(
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
Equivalent to np.isinf


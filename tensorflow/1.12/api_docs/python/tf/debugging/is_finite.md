<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.is_finite" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.is_finite

### Aliases:

* `tf.debugging.is_finite`
* `tf.is_finite`

``` python
tf.debugging.is_finite(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Returns which elements of x are finite.



#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.

#### Numpy Compatibility
Equivalent to np.isfinite


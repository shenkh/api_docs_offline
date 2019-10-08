<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.nextafter" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.nextafter

``` python
tf.math.nextafter(
    x1,
    x2,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Returns the next representable value of `x1` in the direction of `x2`, element-wise.

This operation returns the same result as the C++ std::nextafter function.

It can also return a subnormal number.



#### Args:

* <b>`x1`</b>: A `Tensor`. Must be one of the following types: `float64`, `float32`.
* <b>`x2`</b>: A `Tensor`. Must have the same type as `x1`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x1`.

#### Cpp Compatibility
Equivalent to C++ std::nextafter function.


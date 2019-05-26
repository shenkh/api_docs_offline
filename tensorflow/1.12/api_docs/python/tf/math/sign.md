<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.sign" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.sign

### Aliases:

* `tf.math.sign`
* `tf.sign`

``` python
tf.math.sign(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

Returns an element-wise indication of the sign of a number.

`y = sign(x) = -1` if `x < 0`; 0 if `x == 0` or `tf.is_nan(x)`; 1 if `x > 0`.

Zero is returned for NaN inputs.

For complex numbers, `y = sign(x) = x / |x|` if `x != 0`, otherwise `y = 0`.

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor`. Must be one of the following types: `half`,
    `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor`, respectively. Has the same type as `x`.



#### Numpy Compatibility
Equivalent to numpy.sign except for the behavior for input values of NaN.


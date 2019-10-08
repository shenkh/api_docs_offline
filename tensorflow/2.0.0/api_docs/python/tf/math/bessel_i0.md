<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.bessel_i0" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.bessel_i0

``` python
tf.math.bessel_i0(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/special_math_ops.py`](/code/stable/tensorflow/python/ops/special_math_ops.py).

Computes the Bessel i0 function of `x` element-wise.

Modified Bessel function of order 0.

It is preferable to use the numerically stabler function `i0e(x)` instead.

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor`. Must be one of the following types: `half`,
    `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor`, respectively. Has the same type as `x`.



#### Scipy Compatibility
Equivalent to scipy.special.i0


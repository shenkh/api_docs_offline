<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.bessel_i1e" />
</div>

# tf.math.bessel_i1e

``` python
tf.math.bessel_i1e(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

Computes the Bessel i1e function of `x` element-wise.

Exponentially scaled modified Bessel function of order 1 defined as
`bessel_i1e(x) = exp(-abs(x)) bessel_i1(x)`.

This function is faster and numerically stabler than `bessel_i1(x)`.

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor`. Must be one of the following types: `half`,
    `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor`, respectively. Has the same type as `x`.



#### Scipy Compatibility
Equivalent to scipy.special.i1e


<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.bessel_i1" />
</div>

# tf.math.bessel_i1

``` python
tf.math.bessel_i1(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/special_math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/special_math_ops.py).

Computes the Bessel i1 function of `x` element-wise.

Modified Bessel function of order 1.

It is preferable to use the numerically stabler function `i1e(x)` instead.

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor`. Must be one of the following types: `half`,
    `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor`, respectively. Has the same type as `x`.



#### Scipy Compatibility
Equivalent to scipy.special.i1


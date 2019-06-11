<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.bessel_i1" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.bessel_i1

Computes the Bessel i1 function of `x` element-wise.

### Aliases:

* `tf.compat.v1.math.bessel_i1`
* `tf.compat.v2.math.bessel_i1`
* `tf.math.bessel_i1`

``` python
tf.math.bessel_i1(
    x,
    name=None
)
```



Defined in [`python/ops/special_math_ops.py`](/code/stable/tensorflow/python/ops/special_math_ops.py).

<!-- Placeholder for "Used in" -->

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


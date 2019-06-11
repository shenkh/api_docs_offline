<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.bessel_i1e" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.bessel_i1e

Computes the Bessel i1e function of `x` element-wise.

### Aliases:

* `tf.compat.v1.math.bessel_i1e`
* `tf.compat.v2.math.bessel_i1e`
* `tf.math.bessel_i1e`

``` python
tf.math.bessel_i1e(
    x,
    name=None
)
```



Defined in generated file: `python/ops/gen_math_ops.py`.

<!-- Placeholder for "Used in" -->

Exponentially scaled modified Bessel function of order 0 defined as
`bessel_i1e(x) = exp(-abs(x)) bessel_i1(x)`.

This function is faster and numerically stabler than `bessel_i1(x)`.

#### Args:


* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

If `x` is a `SparseTensor`, returns
`SparseTensor(x.indices, tf.math.bessel_i1e(x.values, ...), x.dense_shape)`

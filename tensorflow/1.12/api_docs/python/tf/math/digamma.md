<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.digamma" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.digamma

### Aliases:

* `tf.digamma`
* `tf.math.digamma`

``` python
tf.math.digamma(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Computes Psi, the derivative of Lgamma (the log of the absolute value of

`Gamma(x)`), element-wise.

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.igamma" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.igamma

Compute the lower regularized incomplete Gamma function `P(a, x)`.

### Aliases:

* `tf.compat.v1.igamma`
* `tf.compat.v1.math.igamma`
* `tf.compat.v2.math.igamma`
* `tf.math.igamma`

``` python
tf.math.igamma(
    a,
    x,
    name=None
)
```



Defined in generated file: `python/ops/gen_math_ops.py`.

<!-- Placeholder for "Used in" -->

The lower regularized incomplete Gamma function is defined as:


\\(P(a, x) = gamma(a, x) / Gamma(a) = 1 - Q(a, x)\\)

where

\\(gamma(a, x) = \\int_{0}^{x} t^{a-1} exp(-t) dt\\)

is the lower incomplete Gamma function.

Note, above `Q(a, x)` (`Igammac`) is the upper regularized complete
Gamma function.

#### Args:


* <b>`a`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`.
* <b>`x`</b>: A `Tensor`. Must have the same type as `a`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `a`.

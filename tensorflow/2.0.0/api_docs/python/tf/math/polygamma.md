<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.polygamma" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.polygamma

``` python
tf.math.polygamma(
    a,
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Compute the polygamma function \\(\psi^{(n)}(x)\\).

The polygamma function is defined as:


\\(\psi^{(a)}(x) = \frac{d^a}{dx^a} \psi(x)\\)

where \\(\psi(x)\\) is the digamma function.
The polygamma function is defined only for non-negative integer orders \\a\\.

#### Args:

* <b>`a`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`.
* <b>`x`</b>: A `Tensor`. Must have the same type as `a`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `a`.
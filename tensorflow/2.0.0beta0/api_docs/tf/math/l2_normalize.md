<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.l2_normalize" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.l2_normalize

Normalizes along dimension `axis` using an L2 norm.

### Aliases:

* `tf.compat.v2.linalg.l2_normalize`
* `tf.compat.v2.math.l2_normalize`
* `tf.compat.v2.nn.l2_normalize`
* `tf.linalg.l2_normalize`
* `tf.math.l2_normalize`
* `tf.nn.l2_normalize`

``` python
tf.math.l2_normalize(
    x,
    axis=None,
    epsilon=1e-12,
    name=None
)
```



Defined in [`python/ops/nn_impl.py`](/code/stable/tensorflow/python/ops/nn_impl.py).

<!-- Placeholder for "Used in" -->

For a 1-D tensor with `axis = 0`, computes

    output = x / sqrt(max(sum(x**2), epsilon))

For `x` with more dimensions, independently normalizes each 1-D slice along
dimension `axis`.

#### Args:


* <b>`x`</b>: A `Tensor`.
* <b>`axis`</b>: Dimension along which to normalize.  A scalar or a vector of
  integers.
* <b>`epsilon`</b>: A lower bound value for the norm. Will use `sqrt(epsilon)` as the
  divisor if `norm < sqrt(epsilon)`.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:

A `Tensor` with the same shape as `x`.

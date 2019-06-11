<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.sigmoid" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.sigmoid

Computes sigmoid of `x` element-wise.

### Aliases:

* `tf.compat.v1.math.sigmoid`
* `tf.compat.v1.nn.sigmoid`
* `tf.compat.v1.sigmoid`
* `tf.compat.v2.math.sigmoid`
* `tf.compat.v2.nn.sigmoid`
* `tf.compat.v2.sigmoid`
* `tf.math.sigmoid`
* `tf.nn.sigmoid`
* `tf.sigmoid`

``` python
tf.math.sigmoid(
    x,
    name=None
)
```



Defined in [`python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

<!-- Placeholder for "Used in" -->

Specifically, `y = 1 / (1 + exp(-x))`.

#### Args:


* <b>`x`</b>: A Tensor with type `float16`, `float32`, `float64`, `complex64`, or
  `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A Tensor with the same type as `x`.




#### Scipy Compatibility
Equivalent to scipy.special.expit


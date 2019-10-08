<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.cos" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.cos

### Aliases:

* `tf.cos`
* `tf.math.cos`

``` python
tf.math.cos(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Computes cos of x element-wise.

  Given an input tensor, this function computes cosine of every
  element in the tensor. Input range is `(-inf, inf)` and
  output range is `[-1,1]`. If input lies outside the boundary, `nan`
  is returned.

  ```python
  x = tf.constant([-float("inf"), -9, -0.5, 1, 1.2, 200, 10000, float("inf")])
  tf.math.cos(x) ==> [nan -0.91113025 0.87758255 0.5403023 0.36235774 0.48718765 -0.95215535 nan]
  ```

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.
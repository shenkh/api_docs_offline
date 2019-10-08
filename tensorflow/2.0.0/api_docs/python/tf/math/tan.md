<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.tan" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.tan

### Aliases:

* `tf.math.tan`
* `tf.tan`

``` python
tf.math.tan(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Computes tan of x element-wise.

  Given an input tensor, this function computes tangent of every
  element in the tensor. Input range is `(-inf, inf)` and
  output range is `(-inf, inf)`. If input lies outside the boundary, `nan`
  is returned.

  ```python
  x = tf.constant([-float("inf"), -9, -0.5, 1, 1.2, 200, 10000, float("inf")])
  tf.math.tan(x) ==> [nan 0.45231566 -0.5463025 1.5574077 2.572152 -1.7925274 0.32097113 nan]
  ```

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.
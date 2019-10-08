<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.atanh" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.atanh

### Aliases:

* `tf.atanh`
* `tf.math.atanh`

``` python
tf.math.atanh(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Computes inverse hyperbolic tangent of x element-wise.

  Given an input tensor, this function computes inverse hyperbolic tangent
  for every element in the tensor. Input range is `[-1,1]` and output range is
  `[-inf, inf]`. If input is `-1`, output will be `-inf` and if the
  input is `1`, output will be `inf`. Values outside the range will have
  `nan` as output.

  ```python
  x = tf.constant([-float("inf"), -1, -0.5, 1, 0, 0.5, 10, float("inf")])
  tf.math.atanh(x) ==> [nan -inf -0.54930615 inf  0. 0.54930615 nan nan]
  ```

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.
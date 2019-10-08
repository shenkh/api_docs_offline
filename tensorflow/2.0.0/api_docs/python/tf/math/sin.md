<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.sin" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.sin

### Aliases:

* `tf.math.sin`
* `tf.sin`

``` python
tf.math.sin(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Computes sine of x element-wise.

  Given an input tensor, this function computes sine of every
  element in the tensor. Input range is `(-inf, inf)` and
  output range is `[-1,1]`.

  ```python
  x = tf.constant([-float("inf"), -9, -0.5, 1, 1.2, 200, 10, float("inf")])
  tf.math.sin(x) ==> [nan -0.4121185 -0.47942555 0.84147096 0.9320391 -0.87329733 -0.54402107 nan]
  ```

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.expm1" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.expm1

``` python
tf.math.expm1(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Computes `exp(x) - 1` element-wise.

  i.e. `exp(x) - 1` or `e^(x) - 1`, where `x` is the input tensor.
  `e` denotes Euler's number and is approximately equal to 2.718281.

  ```python
  x = tf.constant(2.0)
  tf.math.expm1(x) ==> 6.389056

  x = tf.constant([2.0, 8.0])
  tf.math.expm1(x) ==> array([6.389056, 2979.958], dtype=float32)

  x = tf.constant(1 + 1j)
  tf.math.expm1(x) ==> (0.46869393991588515+2.2873552871788423j)
  ```

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.sinh" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.sinh

### Aliases:

* `tf.math.sinh`
* `tf.sinh`

``` python
tf.math.sinh(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Computes hyperbolic sine of x element-wise.

  Given an input tensor, this function computes hyperbolic sine of every
  element in the tensor. Input range is `[-inf,inf]` and output range
  is `[-inf,inf]`.

  ```python
  x = tf.constant([-float("inf"), -9, -0.5, 1, 1.2, 2, 10, float("inf")])
  tf.math.sinh(x) ==> [-inf -4.0515420e+03 -5.2109528e-01 1.1752012e+00 1.5094614e+00 3.6268604e+00 1.1013232e+04 inf]
  ```

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.
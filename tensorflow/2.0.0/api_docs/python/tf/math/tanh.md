<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.tanh" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.tanh

### Aliases:

* `tf.math.tanh`
* `tf.nn.tanh`
* `tf.tanh`

``` python
tf.math.tanh(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Computes hyperbolic tangent of `x` element-wise.

  Given an input tensor, this function computes hyperbolic tangent of every
  element in the tensor. Input range is `[-inf, inf]` and
  output range is `[-1,1]`.

  ```python
  x = tf.constant([-float("inf"), -5, -0.5, 1, 1.2, 2, 3, float("inf")])
  tf.math.tanh(x) ==> [-1. -0.99990916 -0.46211717 0.7615942 0.8336547 0.9640276 0.9950547 1.]
  ```

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

If `x` is a `SparseTensor`, returns
`SparseTensor(x.indices, tf.math.tanh(x.values, ...), x.dense_shape)`
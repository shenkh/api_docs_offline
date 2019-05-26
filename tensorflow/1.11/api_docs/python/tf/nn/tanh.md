<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.tanh" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.tanh

### Aliases:

* `tf.nn.tanh`
* `tf.tanh`

``` python
tf.nn.tanh(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guide: [Neural Network > Activation Functions](../../../../api_guides/python/nn.md#Activation_Functions)

Computes hyperbolic tangent of `x` element-wise.

#### Args:

* <b>`x`</b>: A Tensor or SparseTensor with type `float16`, `float32`, `double`,
    `complex64`, or `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A Tensor or SparseTensor respectively with the same type as `x`.
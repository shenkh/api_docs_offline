<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.log_sigmoid" />
</div>

# tf.log_sigmoid

``` python
tf.log_sigmoid(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

Computes log sigmoid of `x` element-wise.

Specifically, `y = log(1 / (1 + exp(-x)))`.  For numerical stability,
we use `y = -tf.nn.softplus(-x)`.

#### Args:

* <b>`x`</b>: A Tensor with type `float32` or `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A Tensor with the same type as `x`.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.infeed_dequeue_tuple" />
</div>

# tf.contrib.tpu.infeed_dequeue_tuple

``` python
tf.contrib.tpu.infeed_dequeue_tuple(
    dtypes,
    shapes,
    name=None
)
```



Defined in [`tensorflow/contrib/tpu/python/ops/tpu_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/tpu/python/ops/tpu_ops.py).

A placeholder op for values fed into the TPU simultaneously as a tuple.

#### Args:

* <b>`dtypes`</b>: A list of <a href="../../../tf/DType.md"><code>tf.DType</code></a>s that has length `>= 1`.
    The element types of each element in `outputs`.
* <b>`shapes`</b>: A list of shapes (each a <a href="../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> or list of `ints`).
    The shapes of each tensor in `outputs`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A list of `Tensor` objects of type `dtypes`.
A list of tensors that will be provided using the infeed mechanism.


#### Raises:

* <b>`TypeError`</b>: If a type in 'dtypes` is not a supported infeed type.
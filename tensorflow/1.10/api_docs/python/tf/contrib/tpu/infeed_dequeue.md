<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.infeed_dequeue" />
</div>

# tf.contrib.tpu.infeed_dequeue

``` python
tf.contrib.tpu.infeed_dequeue(
    dtype,
    shape,
    name=None
)
```



Defined in [`tensorflow/contrib/tpu/python/ops/tpu_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/tpu/python/ops/tpu_ops.py).

A placeholder op for a value that will be fed into the computation.

#### Args:

* <b>`dtype`</b>: A <a href="../../../tf/DType.md"><code>tf.DType</code></a>. The type of elements in the tensor.
* <b>`shape`</b>: A <a href="../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> or list of `ints`. The shape of the tensor.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `dtype`.
A tensor that will be provided using the infeed mechanism.


#### Raises:

* <b>`TypeError`</b>: If 'dtype` is not a supported infeed type.
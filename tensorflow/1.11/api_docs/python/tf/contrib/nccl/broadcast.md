<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.nccl.broadcast" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.nccl.broadcast

``` python
tf.contrib.nccl.broadcast(tensor)
```



Defined in [`tensorflow/contrib/nccl/python/ops/nccl_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/nccl/python/ops/nccl_ops.py).

Returns a tensor that can be efficiently transferred to other devices.

#### Args:

* <b>`tensor`</b>: The tensor to send; must be assigned to a GPU device.


#### Returns:

A tensor with the value of `src_tensor`, which can be used as input to
ops on other GPU devices.
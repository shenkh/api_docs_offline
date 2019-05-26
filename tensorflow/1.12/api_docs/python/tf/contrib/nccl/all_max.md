<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.nccl.all_max" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.nccl.all_max

``` python
tf.contrib.nccl.all_max(tensors)
```



Defined in [`tensorflow/contrib/nccl/python/ops/nccl_ops.py`](/code/stable/tensorflow/contrib/nccl/python/ops/nccl_ops.py).

Returns a list of tensors with the all-reduce max across `tensors`.

The computation is done with an all-reduce operation, so if only some of the
returned tensors are evaluated then the computation will hang.

#### Args:

* <b>`tensors`</b>: The input tensors across which to reduce; must be assigned
    to GPU devices.


#### Returns:

List of tensors, each with the maximum of the input tensors, where tensor i
has the same device as `tensors[i]`.
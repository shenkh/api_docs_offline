<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.core" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.tpu.core

``` python
tf.contrib.tpu.core(num)
```



Defined in [`tensorflow/contrib/tpu/python/tpu/tpu.py`](https://www.tensorflow.org/code/tensorflow/contrib/tpu/python/tpu/tpu.py).

Returns the device name for a core in a replicated TPU computation.

#### Args:

* <b>`num`</b>: the virtual core number within each replica to which operators should
  be assigned.

#### Returns:

A device name, suitable for passing to `tf.device()`.
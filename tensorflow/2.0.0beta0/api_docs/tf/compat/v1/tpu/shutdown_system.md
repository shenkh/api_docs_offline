<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.tpu.shutdown_system" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.tpu.shutdown_system

Shuts down a running a distributed TPU system.

``` python
tf.compat.v1.tpu.shutdown_system(job=None)
```



Defined in [`python/tpu/tpu.py`](/code/stable/tensorflow/python/tpu/tpu.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`job`</b>: The job (the XXX in TensorFlow device specification /job:XXX) that
  contains the TPU devices that will be shutdown. If job=None it is
  assumed there is only one job in the TensorFlow flock, and an error will
  be returned if this assumption does not hold.
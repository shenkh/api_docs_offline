<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.tpu.core" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.tpu.core

Returns the device name for a core in a replicated TPU computation.

``` python
tf.compat.v1.tpu.core(num)
```



Defined in [`python/tpu/tpu.py`](/code/stable/tensorflow/python/tpu/tpu.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`num`</b>: the virtual core number within each replica to which operators should
be assigned.

#### Returns:

A device name, suitable for passing to `tf.device()`.

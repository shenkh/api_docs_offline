<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.tpu.experimental.initialize_tpu_system" />
<meta itemprop="path" content="Stable" />
</div>

# tf.tpu.experimental.initialize_tpu_system

Initialize the TPU devices.

### Aliases:

* `tf.compat.v1.tpu.experimental.initialize_tpu_system`
* `tf.compat.v2.tpu.experimental.initialize_tpu_system`
* `tf.tpu.experimental.initialize_tpu_system`

``` python
tf.tpu.experimental.initialize_tpu_system(cluster_resolver=None)
```



Defined in [`python/tpu/tpu_strategy_util.py`](/code/stable/tensorflow/python/tpu/tpu_strategy_util.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`cluster_resolver`</b>: A tf.distribute.cluster_resolver.TPUClusterResolver,
    which provides information about the TPU cluster.

#### Returns:

The tf.tpu.Topology object for the topology of the TPU cluster.



#### Raises:


* <b>`RuntimeError`</b>: If no TPU devices found for eager execution.
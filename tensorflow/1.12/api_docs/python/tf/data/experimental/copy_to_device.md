<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.copy_to_device" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.copy_to_device

``` python
tf.data.experimental.copy_to_device(
    target_device,
    source_device='/cpu:0'
)
```



Defined in [`tensorflow/python/data/experimental/ops/prefetching_ops.py`](/code/stable/tensorflow/python/data/experimental/ops/prefetching_ops.py).

A transformation that copies dataset elements to the given `target_device`.

#### Args:

* <b>`target_device`</b>: The name of a device to which elements will be copied.
* <b>`source_device`</b>: The original device on which `input_dataset` will be placed.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.
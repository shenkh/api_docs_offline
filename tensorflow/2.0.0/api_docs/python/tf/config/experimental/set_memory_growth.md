<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental.set_memory_growth" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental.set_memory_growth

``` python
tf.config.experimental.set_memory_growth(
    device,
    enable
)
```



Defined in [`tensorflow/python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

Set if memory growth should be enabled for a PhysicalDevice.

A PhysicalDevice with memory growth set will not allocate all memory on the
device upfront. Memory growth cannot be configured on a PhysicalDevice with
virtual devices configured.

For example:

```python
physical_devices = tf.config.experimental.list_physical_devices('GPU')
assert len(physical_devices) > 0, "Not enough GPU hardware devices available"
tf.config.experimental.set_memory_growth(physical_devices[0], True)
```

#### Args:

* <b>`device`</b>: PhysicalDevice to configure
* <b>`enable`</b>: Whether to enable or disable memory growth
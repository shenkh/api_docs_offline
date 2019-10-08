<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental.set_visible_devices" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental.set_visible_devices

``` python
tf.config.experimental.set_visible_devices(
    devices,
    device_type=None
)
```



Defined in [`tensorflow/python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

Set the list of visible devices.

Sets the list of PhysicalDevices to be marked as visible to the runtime. Any
devices that are not marked as visible means TensorFlow will not allocate
memory on it and will not be able to place any operations on it as no
LogicalDevice will be created on it. By default all discovered devices are
marked as visible.

The following example demonstrates disabling the first GPU on the machine.

```python
physical_devices = config.experimental.list_physical_devices('GPU')
assert len(physical_devices) > 0, "Not enough GPU hardware devices available"
# Disable first GPU
tf.config.experimental.set_visible_devices(physical_devices[1:], 'GPU')
logical_devices = config.experimental.list_logical_devices('GPU')
# Logical device was not created for first GPU
assert len(logical_devices) == len(physical_devices) - 1
```

#### Args:

* <b>`devices`</b>: (optional) List of PhysicalDevice objects to make visible
* <b>`device_type`</b>: (optional) Device types to limit visibility configuration to.
    Other device types will be left unaltered.
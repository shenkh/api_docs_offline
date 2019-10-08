<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental.get_virtual_device_configuration" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental.get_virtual_device_configuration

``` python
tf.config.experimental.get_virtual_device_configuration(device)
```



Defined in [`tensorflow/python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

Get the virtual device configuration for a PhysicalDevice.

Returns the list of VirtualDeviceConfiguration objects previously configured
by a call to `tf.config.experimental.set_virtual_device_configuration()`.

For example:

```python
physical_devices = tf.config.experimental.list_physical_devices('CPU')
assert len(physical_devices) == 1, "No CPUs found"
configs = tf.config.experimental.get_virtual_device_configuration(
    physical_devices[0])
assert configs is None
tf.config.experimental.set_virtual_device_configuration(
    physical_devices[0],
    [tf.config.experimental.VirtualDeviceConfiguration(),
     tf.config.experimental.VirtualDeviceConfiguration()])
configs = tf.config.experimental.get_virtual_device_configuration(
    physical_devices[0])
assert len(configs) == 2
```

#### Args:

* <b>`device`</b>: PhysicalDevice to query


#### Returns:

List of <a href="../../../tf/config/experimental/VirtualDeviceConfiguration.md"><code>tf.config.experimental.VirtualDeviceConfiguration</code></a> objects or
`None` if no virtual device configuration has been set for this physical
device.
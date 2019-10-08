<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental.list_physical_devices" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental.list_physical_devices

``` python
tf.config.experimental.list_physical_devices(device_type=None)
```



Defined in [`tensorflow/python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

Return a list of physical devices visible to the runtime.

Physical devices are hardware devices locally present on the current machine.
By default all discovered CPU and GPU devices are considered visible. The
`list_physical_devices` allows querying the hardware prior to runtime
initialization.

The following example ensures the machine can see at least 1 GPU.

```python
physical_devices = tf.config.experimental.list_physical_devices('GPU')
assert len(physical_devices) > 0, "No GPUs found."
```

#### Args:

* <b>`device_type`</b>: (optional) Device type to filter by such as "CPU" or "GPU"


#### Returns:

List of PhysicalDevice objects
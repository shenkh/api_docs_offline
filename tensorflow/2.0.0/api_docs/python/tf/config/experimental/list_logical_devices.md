<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental.list_logical_devices" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental.list_logical_devices

``` python
tf.config.experimental.list_logical_devices(device_type=None)
```



Defined in [`tensorflow/python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

Return a list of logical devices created by runtime.

Logical devices may correspond to physical devices or remote devices in the
cluster. Operations and tensors may be placed on these devices by using the
`name` of the LogicalDevice.

For example:

```python
logical_devices = tf.config.experimental.list_logical_devices('GPU')
# Allocate on GPU:0
with tf.device(logical_devices[0].name):
  one = tf.constant(1)
# Allocate on GPU:1
with tf.device(logical_devices[1].name):
  two = tf.constant(2)
```

#### Args:

* <b>`device_type`</b>: (optional) Device type to filter by such as "CPU" or "GPU"


#### Returns:

List of LogicalDevice objects
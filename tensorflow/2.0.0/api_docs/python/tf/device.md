<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.device" />
<meta itemprop="path" content="Stable" />
</div>

# tf.device

``` python
tf.device(device_name)
```



Defined in [`tensorflow/python/framework/ops.py`](/code/stable/tensorflow/python/framework/ops.py).

Specifies the device for ops created/executed in this context.

`device_name` can be fully specified, as in "/job:worker/task:1/device:cpu:0",
or partially specified, containing only a subset of the "/"-separated
fields. Any fields which are specified override device annotations from outer
scopes. For example:

```python
with tf.device('/job:foo'):
  # ops created here have devices with /job:foo
  with tf.device('/job:bar/task:0/device:gpu:2'):
    # ops created here have the fully specified device above
  with tf.device('/device:gpu:1'):
    # ops created here have the device '/job:foo/device:gpu:1'
```

#### Args:

* <b>`device_name`</b>: The device name to use in the context.


#### Returns:

A context manager that specifies the default device to use for newly
created ops.


#### Raises:

* <b>`RuntimeError`</b>: If a function is passed in.
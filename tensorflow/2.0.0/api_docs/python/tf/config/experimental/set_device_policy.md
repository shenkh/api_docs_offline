<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental.set_device_policy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental.set_device_policy

``` python
tf.config.experimental.set_device_policy(device_policy)
```



Defined in [`tensorflow/python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

Sets the current thread device policy.

The device policy controls how operations requiring inputs on a specific
device (e.g., on GPU:0) handle inputs on a different device (e.g. GPU:1).

When using the default, an appropriate policy will be picked automatically.
The default policy may change over time.

This function only sets the device policy for the current thread. Any
subsequently started thread will again use the default policy.

#### Args:

* <b>`device_policy`</b>: A device policy.
    Valid values:
    - None: Switch to a system default.
    - 'warn': Copies the tensors which are not on the right device and logs
        a warning.
    - 'explicit': Raises an error if the placement is not as required.
    - 'silent': Silently copies the tensors. Note that this may hide
        performance problems as there is no notification provided when
        operations are blocked on the tensor being copied between devices.
    - 'silent_for_int32': silently copies `int32` tensors, raising errors on
        the other ones.


#### Raises:

* <b>`ValueError`</b>: If an invalid `device_policy` is passed.
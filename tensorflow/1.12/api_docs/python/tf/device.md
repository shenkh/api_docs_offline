<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.device" />
<meta itemprop="path" content="Stable" />
</div>

# tf.device

``` python
tf.device(device_name_or_function)
```



Defined in [`tensorflow/python/framework/ops.py`](/code/stable/tensorflow/python/framework/ops.py).

Wrapper for `Graph.device()` using the default graph.

See
<a href="../tf/Graph.md#device"><code>tf.Graph.device</code></a>
for more details.

#### Args:

* <b>`device_name_or_function`</b>: The device name or function to use in
    the context.


#### Returns:

A context manager that specifies the default device to use for newly
created ops.


#### Raises:

* <b>`RuntimeError`</b>: If eager execution is enabled and a function is passed in.
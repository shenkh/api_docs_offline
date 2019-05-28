<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.container" />
</div>

# tf.container

``` python
tf.container(container_name)
```



Defined in [`tensorflow/python/framework/ops.py`](https://www.tensorflow.org/code/tensorflow/python/framework/ops.py).

See the guide: [Building Graphs > Utility functions](../../../api_guides/python/framework.md#Utility_functions)

Wrapper for `Graph.container()` using the default graph.

#### Args:

* <b>`container_name`</b>: The container string to use in the context.


#### Returns:

A context manager that specifies the default container to use for newly
created stateful ops.
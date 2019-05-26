<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.container" />
<meta itemprop="path" content="Stable" />
</div>

# tf.container

``` python
tf.container(container_name)
```



Defined in [`tensorflow/python/framework/ops.py`](/code/stable/tensorflow/python/framework/ops.py).

Wrapper for `Graph.container()` using the default graph.

#### Args:

* <b>`container_name`</b>: The container string to use in the context.


#### Returns:

A context manager that specifies the default container to use for newly
created stateful ops.
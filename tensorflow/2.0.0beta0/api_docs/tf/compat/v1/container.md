<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.container" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.container

Wrapper for `Graph.container()` using the default graph.

``` python
tf.compat.v1.container(container_name)
```



Defined in [`python/framework/ops.py`](/code/stable/tensorflow/python/framework/ops.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`container_name`</b>: The container string to use in the context.


#### Returns:

A context manager that specifies the default container to use for newly
created stateful ops.

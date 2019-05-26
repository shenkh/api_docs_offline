<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.create_global_step" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.framework.create_global_step

``` python
tf.contrib.framework.create_global_step(graph=None)
```



Defined in [`tensorflow/contrib/framework/python/ops/variables.py`](/code/stable/tensorflow/contrib/framework/python/ops/variables.py).

Create global step tensor in graph. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Please switch to tf.train.create_global_step

This API is deprecated. Use core framework training version instead.

#### Args:

* <b>`graph`</b>: The graph in which to create the global step tensor. If missing,
    use default graph.


#### Returns:

Global step tensor.


#### Raises:

* <b>`ValueError`</b>: if global step tensor is already defined.
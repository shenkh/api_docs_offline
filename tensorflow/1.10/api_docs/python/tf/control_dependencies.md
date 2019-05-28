<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.control_dependencies" />
</div>

# tf.control_dependencies

``` python
tf.control_dependencies(control_inputs)
```



Defined in [`tensorflow/python/framework/ops.py`](https://www.tensorflow.org/code/tensorflow/python/framework/ops.py).

See the guide: [Building Graphs > Utility functions](../../../api_guides/python/framework.md#Utility_functions)

Wrapper for `Graph.control_dependencies()` using the default graph.

See <a href="../tf/Graph.md#control_dependencies"><code>tf.Graph.control_dependencies</code></a>
for more details.

When eager execution is enabled, any callable object in the `control_inputs`
list will be called.

#### Args:

* <b>`control_inputs`</b>: A list of `Operation` or `Tensor` objects which
    must be executed or computed before running the operations
    defined in the context.  Can also be `None` to clear the control
    dependencies. If eager execution is enabled, any callable object in the
    `control_inputs` list will be called.


#### Returns:

A context manager that specifies control dependencies for all
operations constructed within the context.
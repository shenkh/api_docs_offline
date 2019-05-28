<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.add_control_inputs" />
</div>

# tf.contrib.graph_editor.add_control_inputs

``` python
tf.contrib.graph_editor.add_control_inputs(
    op,
    cops
)
```



Defined in [`tensorflow/contrib/graph_editor/reroute.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/reroute.py).

See the guide: [Graph Editor (contrib) > Module: reroute](../../../../../api_guides/python/contrib.graph_editor.md#Module_reroute)

Add the control inputs cops to op.

Warning: this function is directly manipulating the internals of the tf.Graph.

#### Args:

* <b>`op`</b>: a tf.Operation to which the control inputs are added.
* <b>`cops`</b>: an object convertible to a list of <a href="../../../tf/Operation.md"><code>tf.Operation</code></a>.

#### Raises:

* <b>`TypeError`</b>: if op is not a tf.Operation
* <b>`ValueError`</b>: if any cop in cops is already a control input of op.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.add_control_inputs" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.graph_editor.add_control_inputs

``` python
tf.contrib.graph_editor.add_control_inputs(
    op,
    cops
)
```



Defined in [`tensorflow/contrib/graph_editor/reroute.py`](/code/stable/tensorflow/contrib/graph_editor/reroute.py).

Add the control inputs cops to op.

Warning: this function is directly manipulating the internals of the tf.Graph.

#### Args:

* <b>`op`</b>: a tf.Operation to which the control inputs are added.
* <b>`cops`</b>: an object convertible to a list of <a href="../../../tf/Operation.md"><code>tf.Operation</code></a>.

#### Raises:

* <b>`TypeError`</b>: if op is not a tf.Operation
* <b>`ValueError`</b>: if any cop in cops is already a control input of op.
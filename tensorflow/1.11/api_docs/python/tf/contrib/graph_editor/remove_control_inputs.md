<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.remove_control_inputs" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.graph_editor.remove_control_inputs

``` python
tf.contrib.graph_editor.remove_control_inputs(
    op,
    cops
)
```



Defined in [`tensorflow/contrib/graph_editor/reroute.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/reroute.py).

See the guide: [Graph Editor (contrib) > Module: reroute](../../../../../api_guides/python/contrib.graph_editor.md#Module_reroute)

Remove the control inputs cops from co.

Warning: this function is directly manipulating the internals of the
<a href="../../../tf/Graph.md"><code>tf.Graph</code></a>.

#### Args:

* <b>`op`</b>: a <a href="../../../tf/Operation.md"><code>tf.Operation</code></a> from which to remove the control inputs.
* <b>`cops`</b>: an object convertible to a list of <a href="../../../tf/Operation.md"><code>tf.Operation</code></a>.

#### Raises:

* <b>`TypeError`</b>: if op is not a <a href="../../../tf/Operation.md"><code>tf.Operation</code></a>.
* <b>`ValueError`</b>: if any cop in cops is not a control input of op.
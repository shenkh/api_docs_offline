<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.assign_renamed_collections_handler" />
</div>

# tf.contrib.graph_editor.assign_renamed_collections_handler

``` python
tf.contrib.graph_editor.assign_renamed_collections_handler(
    info,
    elem,
    elem_
)
```



Defined in [`tensorflow/contrib/graph_editor/transform.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/transform.py).

See the guide: [Graph Editor (contrib) > Module: transform](../../../../../api_guides/python/contrib.graph_editor.md#Module_transform)

Add the transformed elem to the (renamed) collections of elem.

A collection is renamed only if is not a known key, as described in
<a href="../../../tf/GraphKeys.md"><code>tf.GraphKeys</code></a>.

#### Args:

* <b>`info`</b>: Transform._TmpInfo instance.
* <b>`elem`</b>: the original element (<a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> or <a href="../../../tf/Operation.md"><code>tf.Operation</code></a>)
* <b>`elem_`</b>: the transformed element
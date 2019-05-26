<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.transform_op_if_inside_handler" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.graph_editor.transform_op_if_inside_handler

``` python
tf.contrib.graph_editor.transform_op_if_inside_handler(
    info,
    op,
    keep_if_possible=True
)
```



Defined in [`tensorflow/contrib/graph_editor/transform.py`](/code/stable/tensorflow/contrib/graph_editor/transform.py).

Transform an optional op only if it is inside the subgraph.

This handler is typically use to handle original op: it is fine to keep them
if they are inside the subgraph, otherwise they are just ignored.

#### Args:

* <b>`info`</b>: Transform._TmpInfo instance.
* <b>`op`</b>: the optional op to transform (or ignore).
* <b>`keep_if_possible`</b>: re-attach to the original op if possible, that is,
    if the source graph and the destination graph are the same.

#### Returns:

The transformed op or None.
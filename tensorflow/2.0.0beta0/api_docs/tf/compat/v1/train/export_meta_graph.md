<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.train.export_meta_graph" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.train.export_meta_graph

Returns `MetaGraphDef` proto.

``` python
tf.compat.v1.train.export_meta_graph(
    filename=None,
    meta_info_def=None,
    graph_def=None,
    saver_def=None,
    collection_list=None,
    as_text=False,
    graph=None,
    export_scope=None,
    clear_devices=False,
    clear_extraneous_savers=False,
    strip_default_attrs=False,
    save_debug_info=False,
    **kwargs
)
```



Defined in [`python/training/saver.py`](/code/stable/tensorflow/python/training/saver.py).

<!-- Placeholder for "Used in" -->

Optionally writes it to filename.

This function exports the graph, saver, and collection objects into
`MetaGraphDef` protocol buffer with the intention of it being imported
at a later time or location to restart training, run inference, or be
a subgraph.

#### Args:


* <b>`filename`</b>: Optional filename including the path for writing the generated
  `MetaGraphDef` protocol buffer.
* <b>`meta_info_def`</b>: `MetaInfoDef` protocol buffer.
* <b>`graph_def`</b>: `GraphDef` protocol buffer.
* <b>`saver_def`</b>: `SaverDef` protocol buffer.
* <b>`collection_list`</b>: List of string keys to collect.
* <b>`as_text`</b>: If `True`, writes the `MetaGraphDef` as an ASCII proto.
* <b>`graph`</b>: The `Graph` to export. If `None`, use the default graph.
* <b>`export_scope`</b>: Optional `string`. Name scope under which to extract the
  subgraph. The scope name will be striped from the node definitions for
  easy import later into new name scopes. If `None`, the whole graph is
  exported. graph_def and export_scope cannot both be specified.
* <b>`clear_devices`</b>: Whether or not to clear the device field for an `Operation`
  or `Tensor` during export.
* <b>`clear_extraneous_savers`</b>: Remove any Saver-related information from the graph
  (both Save/Restore ops and SaverDefs) that are not associated with the
  provided SaverDef.
* <b>`strip_default_attrs`</b>: Boolean. If `True`, default-valued attributes will be
  removed from the NodeDefs. For a detailed guide, see
  [Stripping Default-Valued Attributes](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/saved_model/README.md#stripping-default-valued-attributes).
* <b>`save_debug_info`</b>: If `True`, save the GraphDebugInfo to a separate file,
  which in the same directory of filename and with `_debug` added before the
  file extend.
* <b>`**kwargs`</b>: Optional keyed arguments.


#### Returns:

A `MetaGraphDef` proto.



#### Raises:


* <b>`ValueError`</b>: When the `GraphDef` is larger than 2GB.
* <b>`RuntimeError`</b>: If called with eager execution enabled.



#### Eager Compatibility
Exporting/importing meta graphs is not supported unless both `graph_def` and
`graph` are provided. No graph exists when eager execution is enabled.


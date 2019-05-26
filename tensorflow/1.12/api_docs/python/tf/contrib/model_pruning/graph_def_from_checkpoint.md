<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.model_pruning.graph_def_from_checkpoint" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.model_pruning.graph_def_from_checkpoint

``` python
tf.contrib.model_pruning.graph_def_from_checkpoint(
    checkpoint_dir,
    output_node_names
)
```



Defined in [`tensorflow/contrib/model_pruning/python/strip_pruning_vars_lib.py`](/code/stable/tensorflow/contrib/model_pruning/python/strip_pruning_vars_lib.py).

Converts checkpoint data to GraphDef.

Reads the latest checkpoint data and produces a GraphDef in which the
variables have been converted to constants.

#### Args:

* <b>`checkpoint_dir`</b>: Path to the checkpoints.
* <b>`output_node_names`</b>: List of name strings for the result nodes of the graph.


#### Returns:

A GraphDef from the latest checkpoint


#### Raises:

* <b>`ValueError`</b>: if no checkpoint is found
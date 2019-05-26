<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.model_pruning.strip_pruning_vars_fn" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.model_pruning.strip_pruning_vars_fn

``` python
tf.contrib.model_pruning.strip_pruning_vars_fn(
    input_graph_def,
    output_node_names
)
```



Defined in [`tensorflow/contrib/model_pruning/python/strip_pruning_vars_lib.py`](https://www.tensorflow.org/code/tensorflow/contrib/model_pruning/python/strip_pruning_vars_lib.py).

Removes mask variable from the graph.

Replaces the masked_weight tensor with element-wise multiplication of mask
and the corresponding weight variable.

#### Args:

* <b>`input_graph_def`</b>: A GraphDef in which the variables have been converted to
    constants. This is typically the output of
    tf.graph_util.convert_variables_to_constant()
* <b>`output_node_names`</b>: List of name strings for the result nodes of the graph


#### Returns:

A GraphDef in which pruning-related variables have been removed
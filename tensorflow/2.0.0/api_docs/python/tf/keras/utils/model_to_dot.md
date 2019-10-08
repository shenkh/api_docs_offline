<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.model_to_dot" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.utils.model_to_dot

``` python
tf.keras.utils.model_to_dot(
    model,
    show_shapes=False,
    show_layer_names=True,
    rankdir='TB',
    expand_nested=False,
    dpi=96,
    subgraph=False
)
```



Defined in [`tensorflow/python/keras/utils/vis_utils.py`](/code/stable/tensorflow/python/keras/utils/vis_utils.py).

Convert a Keras model to dot format.

#### Arguments:

* <b>`model`</b>: A Keras model instance.
* <b>`show_shapes`</b>: whether to display shape information.
* <b>`show_layer_names`</b>: whether to display layer names.
* <b>`rankdir`</b>: `rankdir` argument passed to PyDot,
      a string specifying the format of the plot:
      'TB' creates a vertical plot;
      'LR' creates a horizontal plot.
* <b>`expand_nested`</b>: whether to expand nested models into clusters.
* <b>`dpi`</b>: Dots per inch.
* <b>`subgraph`</b>: whether to return a `pydot.Cluster` instance.


#### Returns:

A `pydot.Dot` instance representing the Keras model or
a `pydot.Cluster` instance representing nested model if
`subgraph=True`.


#### Raises:

* <b>`ImportError`</b>: if graphviz or pydot are not available.
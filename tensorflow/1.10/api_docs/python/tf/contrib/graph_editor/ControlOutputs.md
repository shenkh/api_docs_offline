<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.ControlOutputs" />
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get"/>
<meta itemprop="property" content="get_all"/>
<meta itemprop="property" content="update"/>
</div>

# tf.contrib.graph_editor.ControlOutputs

## Class `ControlOutputs`





Defined in [`tensorflow/contrib/graph_editor/util.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/util.py).

See the guide: [Graph Editor (contrib) > Module: util](../../../../../api_guides/python/contrib.graph_editor.md#Module_util)

The control outputs topology.

## Properties

<h3 id="graph"><code>graph</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(graph)
```

Create a dictionary of control-output dependencies.

#### Args:

* <b>`graph`</b>: a <a href="../../../tf/Graph.md"><code>tf.Graph</code></a>.

#### Returns:

A dictionary where a key is a <a href="../../../tf/Operation.md"><code>tf.Operation</code></a> instance and the
   corresponding value is a list of all the ops which have the key
   as one of their control-input dependencies.

#### Raises:

* <b>`TypeError`</b>: graph is not a <a href="../../../tf/Graph.md"><code>tf.Graph</code></a>.

<h3 id="get"><code>get</code></h3>

``` python
get(op)
```

return the control outputs of op.

<h3 id="get_all"><code>get_all</code></h3>

``` python
get_all()
```



<h3 id="update"><code>update</code></h3>

``` python
update()
```

Update the control outputs if the graph has changed.




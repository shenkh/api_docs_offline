<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.nn.rnn_cell.MultiRNNCell" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="output_size"/>
<meta itemprop="property" content="scope_name"/>
<meta itemprop="property" content="state_size"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_initial_state"/>
<meta itemprop="property" content="zero_state"/>
</div>

# tf.compat.v1.nn.rnn_cell.MultiRNNCell

## Class `MultiRNNCell`

RNN cell composed sequentially of multiple simple cells.

Inherits From: [`RNNCell`](../../../../../tf/compat/v1/nn/rnn_cell/RNNCell.md)



Defined in [`python/ops/rnn_cell_impl.py`](/code/stable/tensorflow/python/ops/rnn_cell_impl.py).

<!-- Placeholder for "Used in" -->


#### Example:



```python
num_units = [128, 64]
cells = [BasicLSTMCell(num_units=n) for n in num_units]
stacked_rnn_cell = MultiRNNCell(cells)
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    cells,
    state_is_tuple=True
)
```

Create a RNN cell composed sequentially of a number of RNNCells. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
This class is equivalent as tf.keras.layers.StackedRNNCells, and will be replaced by that in Tensorflow 2.0.

#### Args:


* <b>`cells`</b>: list of RNNCells that will be composed in this order.
* <b>`state_is_tuple`</b>: If True, accepted and returned states are n-tuples, where
  `n = len(cells)`.  If False, the states are all concatenated along the
  column axis.  This latter behavior will soon be deprecated.


#### Raises:


* <b>`ValueError`</b>: if cells is empty (not allowed), or at least one of the cells
  returns a state tuple but the flag `state_is_tuple` is `False`.



## Properties

<h3 id="graph"><code>graph</code></h3>

DEPRECATED FUNCTION

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Stop using this property because tf.layers layers no longer track their graph.

<h3 id="output_size"><code>output_size</code></h3>

Integer or TensorShape: size of outputs produced by this cell.


<h3 id="scope_name"><code>scope_name</code></h3>




<h3 id="state_size"><code>state_size</code></h3>

size(s) of state(s) used by this cell.

It can be represented by an Integer, a TensorShape or a tuple of Integers
or TensorShapes.



## Methods

<h3 id="get_initial_state"><code>get_initial_state</code></h3>

``` python
get_initial_state(
    inputs=None,
    batch_size=None,
    dtype=None
)
```




<h3 id="zero_state"><code>zero_state</code></h3>

``` python
zero_state(
    batch_size,
    dtype
)
```

Return zero-filled state tensor(s).


#### Args:


* <b>`batch_size`</b>: int, float, or unit Tensor representing the batch size.
* <b>`dtype`</b>: the data type to use for the state.


#### Returns:

If `state_size` is an int or TensorShape, then the return value is a
`N-D` tensor of shape `[batch_size, state_size]` filled with zeros.

If `state_size` is a nested list or tuple, then the return value is
a nested list or tuple (of the same structure) of `2-D` tensors with
the shapes `[batch_size, s]` for each s in `state_size`.





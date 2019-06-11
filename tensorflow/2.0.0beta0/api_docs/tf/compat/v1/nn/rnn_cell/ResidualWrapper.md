<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.nn.rnn_cell.ResidualWrapper" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="output_size"/>
<meta itemprop="property" content="scope_name"/>
<meta itemprop="property" content="state_size"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_initial_state"/>
<meta itemprop="property" content="zero_state"/>
</div>

# tf.compat.v1.nn.rnn_cell.ResidualWrapper

## Class `ResidualWrapper`

RNNCell wrapper that ensures cell inputs are added to the outputs.





Defined in [`python/ops/rnn_cell_impl.py`](/code/stable/tensorflow/python/ops/rnn_cell_impl.py).

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    *args,
    **kwargs
)
```

Constructs a `ResidualWrapper` for `cell`.


#### Args:


* <b>`cell`</b>: An instance of `RNNCell`.
* <b>`residual_fn`</b>: (Optional) The function to map raw cell inputs and raw cell
  outputs to the actual cell outputs of the residual network.
  Defaults to calling nest.map_structure on (lambda i, o: i + o), inputs
    and outputs.
* <b>`**kwargs`</b>: dict of keyword arguments for base layer.



## Properties

<h3 id="graph"><code>graph</code></h3>

DEPRECATED FUNCTION

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Stop using this property because tf.layers layers no longer track their graph.

<h3 id="output_size"><code>output_size</code></h3>




<h3 id="scope_name"><code>scope_name</code></h3>




<h3 id="state_size"><code>state_size</code></h3>






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







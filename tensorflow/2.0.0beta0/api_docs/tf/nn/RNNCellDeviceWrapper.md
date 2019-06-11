<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.RNNCellDeviceWrapper" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="output_size"/>
<meta itemprop="property" content="state_size"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_initial_state"/>
<meta itemprop="property" content="zero_state"/>
</div>

# tf.nn.RNNCellDeviceWrapper

## Class `RNNCellDeviceWrapper`

Operator that ensures an RNNCell runs on a particular device.



### Aliases:

* Class `tf.compat.v2.nn.RNNCellDeviceWrapper`
* Class `tf.nn.RNNCellDeviceWrapper`



Defined in [`python/keras/layers/rnn_cell_wrapper_v2.py`](/code/stable/tensorflow/python/keras/layers/rnn_cell_wrapper_v2.py).

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    *args,
    **kwargs
)
```

Construct a `DeviceWrapper` for `cell` with device `device`.

Ensures the wrapped `cell` is called with `tf.device(device)`.

#### Args:


* <b>`cell`</b>: An instance of `RNNCell`.
* <b>`device`</b>: A device string or function, for passing to <a href="../../tf/device.md"><code>tf.device</code></a>.
* <b>`**kwargs`</b>: dict of keyword arguments for base layer.



## Properties

<h3 id="output_size"><code>output_size</code></h3>




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







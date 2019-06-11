<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.layers.MaxPooling2D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="scope_name"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.compat.v1.layers.MaxPooling2D

## Class `MaxPooling2D`

Max pooling layer for 2D inputs (e.g. images).

Inherits From: [`MaxPool2D`](../../../../tf/keras/layers/MaxPool2D.md), [`Layer`](../../../../tf/compat/v1/layers/Layer.md)



Defined in [`python/layers/pooling.py`](/code/stable/tensorflow/python/layers/pooling.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`pool_size`</b>: An integer or tuple/list of 2 integers: (pool_height, pool_width)
  specifying the size of the pooling window.
  Can be a single integer to specify the same value for
  all spatial dimensions.
* <b>`strides`</b>: An integer or tuple/list of 2 integers,
  specifying the strides of the pooling operation.
  Can be a single integer to specify the same value for
  all spatial dimensions.
* <b>`padding`</b>: A string. The padding method, either 'valid' or 'same'.
  Case-insensitive.
* <b>`data_format`</b>: A string. The ordering of the dimensions in the inputs.
  `channels_last` (default) and `channels_first` are supported.
  `channels_last` corresponds to inputs with shape
  `(batch, height, width, channels)` while `channels_first` corresponds to
  inputs with shape `(batch, channels, height, width)`.
* <b>`name`</b>: A string, the name of the layer.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    pool_size,
    strides,
    padding='valid',
    data_format='channels_last',
    name=None,
    **kwargs
)
```






## Properties

<h3 id="graph"><code>graph</code></h3>

DEPRECATED FUNCTION

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Stop using this property because tf.layers layers no longer track their graph.

<h3 id="scope_name"><code>scope_name</code></h3>







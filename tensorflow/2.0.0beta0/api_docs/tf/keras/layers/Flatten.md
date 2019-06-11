<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Flatten" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.Flatten

## Class `Flatten`

Flattens the input. Does not affect the batch size.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

### Aliases:

* Class `tf.compat.v1.keras.layers.Flatten`
* Class `tf.compat.v2.keras.layers.Flatten`
* Class `tf.keras.layers.Flatten`



Defined in [`python/keras/layers/core.py`](/code/stable/tensorflow/python/keras/layers/core.py).

<!-- Placeholder for "Used in" -->

If inputs are shaped `(batch,)` without a channel dimension, then flattening
adds an extra channel dimension and output shapes are `(batch, 1)`.

#### Arguments:


* <b>`data_format`</b>: A string,
  one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch, ..., channels)` while `channels_first` corresponds to
  inputs with shape `(batch, channels, ...)`.
  It defaults to the `image_data_format` value found in your
  Keras config file at `~/.keras/keras.json`.
  If you never set it, then it will be "channels_last".


#### Example:



```python
model = Sequential()
model.add(Convolution2D(64, 3, 3,
                        border_mode='same',
                        input_shape=(3, 32, 32)))
# now: model.output_shape == (None, 64, 32, 32)

model.add(Flatten())
# now: model.output_shape == (None, 65536)
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    data_format=None,
    **kwargs
)
```







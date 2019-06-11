<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.MaxPool2D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.MaxPool2D

## Class `MaxPool2D`

Max pooling operation for spatial data.



### Aliases:

* Class `tf.compat.v1.keras.layers.MaxPool2D`
* Class `tf.compat.v1.keras.layers.MaxPooling2D`
* Class `tf.compat.v2.keras.layers.MaxPool2D`
* Class `tf.compat.v2.keras.layers.MaxPooling2D`
* Class `tf.keras.layers.MaxPool2D`
* Class `tf.keras.layers.MaxPooling2D`



Defined in [`python/keras/layers/pooling.py`](/code/stable/tensorflow/python/keras/layers/pooling.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`pool_size`</b>: integer or tuple of 2 integers,
  factors by which to downscale (vertical, horizontal).
  `(2, 2)` will halve the input in both spatial dimension.
  If only one integer is specified, the same window length
  will be used for both dimensions.
* <b>`strides`</b>: Integer, tuple of 2 integers, or None.
  Strides values.
  If None, it will default to `pool_size`.
* <b>`padding`</b>: One of `"valid"` or `"same"` (case-insensitive).
* <b>`data_format`</b>: A string,
  one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch, height, width, channels)` while `channels_first`
  corresponds to inputs with shape
  `(batch, channels, height, width)`.
  It defaults to the `image_data_format` value found in your
  Keras config file at `~/.keras/keras.json`.
  If you never set it, then it will be "channels_last".


#### Input shape:

- If `data_format='channels_last'`:
  4D tensor with shape `(batch_size, rows, cols, channels)`.
- If `data_format='channels_first'`:
  4D tensor with shape `(batch_size, channels, rows, cols)`.



#### Output shape:

- If `data_format='channels_last'`:
  4D tensor with shape `(batch_size, pooled_rows, pooled_cols, channels)`.
- If `data_format='channels_first'`:
  4D tensor with shape `(batch_size, channels, pooled_rows, pooled_cols)`.


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    pool_size=(2, 2),
    strides=None,
    padding='valid',
    data_format=None,
    **kwargs
)
```







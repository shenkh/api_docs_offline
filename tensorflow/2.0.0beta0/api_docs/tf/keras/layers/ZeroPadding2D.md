<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.ZeroPadding2D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.ZeroPadding2D

## Class `ZeroPadding2D`

Zero-padding layer for 2D input (e.g. picture).

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

### Aliases:

* Class `tf.compat.v1.keras.layers.ZeroPadding2D`
* Class `tf.compat.v2.keras.layers.ZeroPadding2D`
* Class `tf.keras.layers.ZeroPadding2D`



Defined in [`python/keras/layers/convolutional.py`](/code/stable/tensorflow/python/keras/layers/convolutional.py).

<!-- Placeholder for "Used in" -->

This layer can add rows and columns of zeros
at the top, bottom, left and right side of an image tensor.

#### Arguments:


* <b>`padding`</b>: Int, or tuple of 2 ints, or tuple of 2 tuples of 2 ints.
  - If int: the same symmetric padding
    is applied to height and width.
  - If tuple of 2 ints:
    interpreted as two different
    symmetric padding values for height and width:
    `(symmetric_height_pad, symmetric_width_pad)`.
  - If tuple of 2 tuples of 2 ints:
    interpreted as
    `((top_pad, bottom_pad), (left_pad, right_pad))`
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

4D tensor with shape:
- If `data_format` is `"channels_last"`:
    `(batch, rows, cols, channels)`
- If `data_format` is `"channels_first"`:
    `(batch, channels, rows, cols)`



#### Output shape:

4D tensor with shape:
- If `data_format` is `"channels_last"`:
    `(batch, padded_rows, padded_cols, channels)`
- If `data_format` is `"channels_first"`:
    `(batch, channels, padded_rows, padded_cols)`


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    padding=(1, 1),
    data_format=None,
    **kwargs
)
```







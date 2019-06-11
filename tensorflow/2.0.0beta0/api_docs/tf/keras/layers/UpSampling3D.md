<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.UpSampling3D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.UpSampling3D

## Class `UpSampling3D`

Upsampling layer for 3D inputs.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

### Aliases:

* Class `tf.compat.v1.keras.layers.UpSampling3D`
* Class `tf.compat.v2.keras.layers.UpSampling3D`
* Class `tf.keras.layers.UpSampling3D`



Defined in [`python/keras/layers/convolutional.py`](/code/stable/tensorflow/python/keras/layers/convolutional.py).

<!-- Placeholder for "Used in" -->

Repeats the 1st, 2nd and 3rd dimensions
of the data by `size[0]`, `size[1]` and `size[2]` respectively.

#### Arguments:


* <b>`size`</b>: Int, or tuple of 3 integers.
  The upsampling factors for dim1, dim2 and dim3.
* <b>`data_format`</b>: A string,
  one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch, spatial_dim1, spatial_dim2, spatial_dim3, channels)`
  while `channels_first` corresponds to inputs with shape
  `(batch, channels, spatial_dim1, spatial_dim2, spatial_dim3)`.
  It defaults to the `image_data_format` value found in your
  Keras config file at `~/.keras/keras.json`.
  If you never set it, then it will be "channels_last".


#### Input shape:

5D tensor with shape:
- If `data_format` is `"channels_last"`:
    `(batch, dim1, dim2, dim3, channels)`
- If `data_format` is `"channels_first"`:
    `(batch, channels, dim1, dim2, dim3)`



#### Output shape:

5D tensor with shape:
- If `data_format` is `"channels_last"`:
    `(batch, upsampled_dim1, upsampled_dim2, upsampled_dim3, channels)`
- If `data_format` is `"channels_first"`:
    `(batch, channels, upsampled_dim1, upsampled_dim2, upsampled_dim3)`


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    size=(2, 2, 2),
    data_format=None,
    **kwargs
)
```







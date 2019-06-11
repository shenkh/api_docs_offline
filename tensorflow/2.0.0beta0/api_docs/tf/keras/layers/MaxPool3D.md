<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.MaxPool3D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.MaxPool3D

## Class `MaxPool3D`

Max pooling operation for 3D data (spatial or spatio-temporal).



### Aliases:

* Class `tf.compat.v1.keras.layers.MaxPool3D`
* Class `tf.compat.v1.keras.layers.MaxPooling3D`
* Class `tf.compat.v2.keras.layers.MaxPool3D`
* Class `tf.compat.v2.keras.layers.MaxPooling3D`
* Class `tf.keras.layers.MaxPool3D`
* Class `tf.keras.layers.MaxPooling3D`



Defined in [`python/keras/layers/pooling.py`](/code/stable/tensorflow/python/keras/layers/pooling.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`pool_size`</b>: Tuple of 3 integers,
  factors by which to downscale (dim1, dim2, dim3).
  `(2, 2, 2)` will halve the size of the 3D input in each dimension.
* <b>`strides`</b>: tuple of 3 integers, or None. Strides values.
* <b>`padding`</b>: One of `"valid"` or `"same"` (case-insensitive).
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

- If `data_format='channels_last'`:
  5D tensor with shape:
  `(batch_size, spatial_dim1, spatial_dim2, spatial_dim3, channels)`
- If `data_format='channels_first'`:
  5D tensor with shape:
  `(batch_size, channels, spatial_dim1, spatial_dim2, spatial_dim3)`



#### Output shape:

- If `data_format='channels_last'`:
  5D tensor with shape:
  `(batch_size, pooled_dim1, pooled_dim2, pooled_dim3, channels)`
- If `data_format='channels_first'`:
  5D tensor with shape:
  `(batch_size, channels, pooled_dim1, pooled_dim2, pooled_dim3)`


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    pool_size=(2, 2, 2),
    strides=None,
    padding='valid',
    data_format=None,
    **kwargs
)
```







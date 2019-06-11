<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.layers.flatten" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.layers.flatten

Flattens an input tensor while preserving the batch axis (axis 0). (deprecated)

``` python
tf.compat.v1.layers.flatten(
    inputs,
    name=None,
    data_format='channels_last'
)
```



Defined in [`python/layers/core.py`](/code/stable/tensorflow/python/layers/core.py).

<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use keras.layers.flatten instead.

#### Arguments:


* <b>`inputs`</b>: Tensor input.
* <b>`name`</b>: The name of the layer (string).
* <b>`data_format`</b>: A string, one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch, height, width, channels)` while `channels_first` corresponds to
  inputs with shape `(batch, channels, height, width)`.


#### Returns:

Reshaped tensor.



#### Examples:



```
  x = tf.compat.v1.placeholder(shape=(None, 4, 4), dtype='float32')
  y = flatten(x)
  # now `y` has shape `(None, 16)`

  x = tf.compat.v1.placeholder(shape=(None, 3, None), dtype='float32')
  y = flatten(x)
  # now `y` has shape `(None, None)`
```
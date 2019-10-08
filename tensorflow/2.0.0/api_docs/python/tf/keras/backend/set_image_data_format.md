<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.set_image_data_format" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.set_image_data_format

``` python
tf.keras.backend.set_image_data_format(data_format)
```



Defined in [`tensorflow/python/keras/backend_config.py`](/code/stable/tensorflow/python/keras/backend_config.py).

Sets the value of the image data format convention.

#### Arguments:

* <b>`data_format`</b>: string. `'channels_first'` or `'channels_last'`.
Example: ```python from keras import backend as K K.image_data_format() >>>
  'channels_first' K.set_image_data_format('channels_last')
  K.image_data_format() >>> 'channels_last' ```


#### Raises:

* <b>`ValueError`</b>: In case of invalid `data_format` value.
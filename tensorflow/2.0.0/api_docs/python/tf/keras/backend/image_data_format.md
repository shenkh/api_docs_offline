<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.image_data_format" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.image_data_format

``` python
tf.keras.backend.image_data_format()
```



Defined in [`tensorflow/python/keras/backend_config.py`](/code/stable/tensorflow/python/keras/backend_config.py).

Returns the default image data format convention.

#### Returns:

    A string, either `'channels_first'` or `'channels_last'`

Example:
```python
keras.backend.image_data_format() >>> 'channels_first'
```
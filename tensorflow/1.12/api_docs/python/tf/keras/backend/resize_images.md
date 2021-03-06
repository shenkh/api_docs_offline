<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.resize_images" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.resize_images

``` python
tf.keras.backend.resize_images(
    x,
    height_factor,
    width_factor,
    data_format
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Resizes the images contained in a 4D tensor.

#### Arguments:

* <b>`x`</b>: Tensor or variable to resize.
* <b>`height_factor`</b>: Positive integer.
* <b>`width_factor`</b>: Positive integer.
* <b>`data_format`</b>: One of `"channels_first"`, `"channels_last"`.


#### Returns:

A tensor.


#### Raises:

* <b>`ValueError`</b>: if `data_format` is neither
        `channels_last` or `channels_first`.
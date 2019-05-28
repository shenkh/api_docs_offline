<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image.random_brightness" />
</div>

# tf.keras.preprocessing.image.random_brightness

``` python
tf.keras.preprocessing.image.random_brightness(
    x,
    brightness_range
)
```



Defined in [`tensorflow/python/keras/preprocessing/image.py`](https://www.tensorflow.org/code/tensorflow/python/keras/preprocessing/image.py).

Performs a random adjustment of brightness of a Numpy image tensor.

#### Arguments:

* <b>`x`</b>: Input tensor. Must be 3D.
* <b>`brightness_range`</b>: Tuple of floats; range to pick a brightness value from.


#### Returns:

Brightness adjusted Numpy image tensor.


#### Raises:

* <b>`ValueError`</b>: if `brightness_range` isn't a tuple.
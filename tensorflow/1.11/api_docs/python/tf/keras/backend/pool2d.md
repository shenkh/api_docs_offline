<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.pool2d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.pool2d

``` python
tf.keras.backend.pool2d(
    x,
    pool_size,
    strides=(1, 1),
    padding='valid',
    data_format=None,
    pool_mode='max'
)
```



Defined in [`tensorflow/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/backend.py).

2D Pooling.

#### Arguments:

* <b>`x`</b>: Tensor or variable.
* <b>`pool_size`</b>: tuple of 2 integers.
* <b>`strides`</b>: tuple of 2 integers.
* <b>`padding`</b>: string, `"same"` or `"valid"`.
* <b>`data_format`</b>: string, `"channels_last"` or `"channels_first"`.
* <b>`pool_mode`</b>: string, `"max"` or `"avg"`.


#### Returns:

A tensor, result of 2D pooling.


#### Raises:

* <b>`ValueError`</b>: if `data_format` is neither `"channels_last"` or
    `"channels_first"`.
* <b>`ValueError`</b>: if `pool_mode` is neither `"max"` or `"avg"`.
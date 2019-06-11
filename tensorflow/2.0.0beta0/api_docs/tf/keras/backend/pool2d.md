<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.pool2d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.pool2d

2D Pooling.

### Aliases:

* `tf.compat.v1.keras.backend.pool2d`
* `tf.compat.v2.keras.backend.pool2d`
* `tf.keras.backend.pool2d`

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



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


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
* <b>`ValueError`</b>: if `pool_size` is not a tuple of 2 integers.
* <b>`ValueError`</b>: if `strides` is not a tuple of 2 integers.
* <b>`ValueError`</b>: if `pool_mode` is neither `"max"` or `"avg"`.
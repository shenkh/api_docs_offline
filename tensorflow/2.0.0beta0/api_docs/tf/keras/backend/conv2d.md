<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.conv2d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.conv2d

2D convolution.

### Aliases:

* `tf.compat.v1.keras.backend.conv2d`
* `tf.compat.v2.keras.backend.conv2d`
* `tf.keras.backend.conv2d`

``` python
tf.keras.backend.conv2d(
    x,
    kernel,
    strides=(1, 1),
    padding='valid',
    data_format=None,
    dilation_rate=(1, 1)
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`kernel`</b>: kernel tensor.
* <b>`strides`</b>: strides tuple.
* <b>`padding`</b>: string, `"same"` or `"valid"`.
* <b>`data_format`</b>: `"channels_last"` or `"channels_first"`.
* <b>`dilation_rate`</b>: tuple of 2 integers.


#### Returns:

A tensor, result of 2D convolution.



#### Raises:


* <b>`ValueError`</b>: if `data_format` is neither `channels_last` or
`channels_first`.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.conv2d_transpose" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.conv2d_transpose

``` python
tf.keras.backend.conv2d_transpose(
    x,
    kernel,
    output_shape,
    strides=(1, 1),
    padding='valid',
    data_format=None
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

2D deconvolution (i.e.

transposed convolution).

#### Arguments:

* <b>`x`</b>: Tensor or variable.
* <b>`kernel`</b>: kernel tensor.
* <b>`output_shape`</b>: 1D int tensor for the output shape.
* <b>`strides`</b>: strides tuple.
* <b>`padding`</b>: string, `"same"` or `"valid"`.
* <b>`data_format`</b>: string, `"channels_last"` or `"channels_first"`.
        Whether to use Theano or TensorFlow/CNTK data format
        for inputs/kernels/outputs.


#### Returns:

A tensor, result of transposed 2D convolution.


#### Raises:

* <b>`ValueError`</b>: if `data_format` is neither `channels_last` or
    `channels_first`.
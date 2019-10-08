<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.conv3d_transpose" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.conv3d_transpose

``` python
tf.nn.conv3d_transpose(
    input,
    filters,
    output_shape,
    strides,
    padding='SAME',
    data_format='NDHWC',
    dilations=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/nn_ops.py`](/code/stable/tensorflow/python/ops/nn_ops.py).

The transpose of `conv3d`.

This operation is sometimes called "deconvolution" after [Deconvolutional
Networks](http://www.matthewzeiler.com/pubs/cvpr2010/cvpr2010.pdf), but is
actually the transpose (gradient) of `conv2d` rather than an actual
deconvolution.

#### Args:

* <b>`input`</b>: A 5-D `Tensor` of type `float` and shape `[batch, height, width,
    in_channels]` for `NHWC` data format or `[batch, in_channels, height,
    width]` for `NCHW` data format.
* <b>`filters`</b>: A 5-D `Tensor` with the same type as `value` and shape `[height,
    width, output_channels, in_channels]`.  `filter`'s `in_channels` dimension
    must match that of `value`.
* <b>`output_shape`</b>: A 1-D `Tensor` representing the output shape of the
    deconvolution op.
* <b>`strides`</b>: An int or list of `ints` that has length `1`, `3` or `5`.  The
    stride of the sliding window for each dimension of `input`. If a single
    value is given it is replicated in the `D`, `H` and `W` dimension. By
    default the `N` and `C` dimensions are set to 0. The dimension order is
    determined by the value of `data_format`, see below for details.
* <b>`padding`</b>: A string, either `'VALID'` or `'SAME'`. The padding algorithm. See
    the "returns" section of <a href="../../tf/nn/convolution.md"><code>tf.nn.convolution</code></a> for details.
* <b>`data_format`</b>: A string. 'NDHWC' and 'NCDHW' are supported.
* <b>`dilations`</b>: An int or list of `ints` that has length `1`, `3` or `5`,
    defaults to 1. The dilation factor for each dimension of`input`. If a
    single value is given it is replicated in the `D`, `H` and `W` dimension.
    By default the `N` and `C` dimensions are set to 1. If set to k > 1, there
    will be k-1 skipped cells between each filter element on that dimension.
    The dimension order is determined by the value of `data_format`, see above
    for details. Dilations in the batch and depth dimensions if a 5-d tensor
    must be 1.
* <b>`name`</b>: Optional name for the returned tensor.


#### Returns:

A `Tensor` with the same type as `value`.
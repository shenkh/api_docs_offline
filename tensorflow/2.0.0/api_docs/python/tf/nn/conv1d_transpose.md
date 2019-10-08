<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.conv1d_transpose" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.conv1d_transpose

``` python
tf.nn.conv1d_transpose(
    input,
    filters,
    output_shape,
    strides,
    padding='SAME',
    data_format='NWC',
    dilations=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/nn_ops.py`](/code/stable/tensorflow/python/ops/nn_ops.py).

The transpose of `conv1d`.

This operation is sometimes called "deconvolution" after [Deconvolutional
Networks](https://www.matthewzeiler.com/mattzeiler/deconvolutionalnetworks.pdf),
but is really the transpose (gradient) of `conv1d` rather than an actual
deconvolution.

#### Args:

* <b>`input`</b>: A 3-D `Tensor` of type `float` and shape
    `[batch, in_width, in_channels]` for `NWC` data format or
    `[batch, in_channels, in_width]` for `NCW` data format.
* <b>`filters`</b>: A 3-D `Tensor` with the same type as `value` and shape
    `[filter_width, output_channels, in_channels]`.  `filter`'s
    `in_channels` dimension must match that of `value`.
* <b>`output_shape`</b>: A 1-D `Tensor`, containing three elements, representing the
    output shape of the deconvolution op.
* <b>`strides`</b>: An int or list of `ints` that has length `1` or `3`.  The number of
    entries by which the filter is moved right at each step.
* <b>`padding`</b>: A string, either `'VALID'` or `'SAME'`. The padding algorithm.
    See the "returns" section of <a href="../../tf/nn/convolution.md"><code>tf.nn.convolution</code></a> for details.
* <b>`data_format`</b>: A string. `'NWC'` and `'NCW'` are supported.
* <b>`dilations`</b>: An int or list of `ints` that has length `1` or `3` which
    defaults to 1. The dilation factor for each dimension of input. If set to
    k > 1, there will be k-1 skipped cells between each filter element on that
    dimension. Dilations in the batch and depth dimensions must be 1.
* <b>`name`</b>: Optional name for the returned tensor.


#### Returns:

A `Tensor` with the same type as `value`.


#### Raises:

* <b>`ValueError`</b>: If input/output depth does not match `filter`'s shape, if
    `output_shape` is not at 3-element vector, if `padding` is other than
    `'VALID'` or `'SAME'`, or if `data_format` is invalid.
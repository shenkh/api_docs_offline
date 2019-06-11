<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.nn.conv2d_backprop_input" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.nn.conv2d_backprop_input

Computes the gradients of convolution with respect to the input.

``` python
tf.compat.v1.nn.conv2d_backprop_input(
    input_sizes,
    filter=None,
    out_backprop=None,
    strides=None,
    padding=None,
    use_cudnn_on_gpu=True,
    data_format='NHWC',
    dilations=[1, 1, 1, 1],
    name=None,
    filters=None
)
```



Defined in [`python/ops/nn_ops.py`](/code/stable/tensorflow/python/ops/nn_ops.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`input_sizes`</b>: A `Tensor` of type `int32`.
  An integer vector representing the shape of `input`,
  where `input` is a 4-D `[batch, height, width, channels]` tensor.
* <b>`filter`</b>: A `Tensor`. Must be one of the following types:
  `half`, `bfloat16`, `float32`, `float64`.
  4-D with shape
  `[filter_height, filter_width, in_channels, out_channels]`.
* <b>`out_backprop`</b>: A `Tensor`. Must have the same type as `filter`.
  4-D with shape `[batch, out_height, out_width, out_channels]`.
  Gradients w.r.t. the output of the convolution.
* <b>`strides`</b>: A list of `ints`.
  The stride of the sliding window for each dimension of the input
  of the convolution. Must be in the same order as the dimension specified
  with format.
* <b>`padding`</b>: Either the `string `"SAME"` or `"VALID"` indicating the type of
  padding algorithm to use, or a list indicating the explicit paddings at
  the start and end of each dimension. When explicit padding is used and
  data_format is `"NHWC"`, this should be in the form `[[0, 0], [pad_top,
  pad_bottom], [pad_left, pad_right], [0, 0]]`. When explicit padding used
  and data_format is `"NCHW"`, this should be in the form `[[0, 0], [0, 0],
  [pad_top, pad_bottom], [pad_left, pad_right]]`.
* <b>`use_cudnn_on_gpu`</b>: An optional `bool`. Defaults to `True`.
* <b>`data_format`</b>: An optional `string` from: `"NHWC", "NCHW"`.
  Defaults to `"NHWC"`.
  Specify the data format of the input and output data. With the
  default format "NHWC", the data is stored in the order of:
      [batch, in_height, in_width, in_channels].
  Alternatively, the format could be "NCHW", the data storage order of:
      [batch, in_channels, in_height, in_width].
* <b>`dilations`</b>: An optional list of `ints`. Defaults to `[1, 1, 1, 1]`.
  1-D tensor of length 4.  The dilation factor for each dimension of
  `input`. If set to k > 1, there will be k-1 skipped cells between each
  filter element on that dimension. The dimension order is determined by
  the value of `data_format`, see above for details. Dilations in the batch
  and depth dimensions must be 1.
* <b>`name`</b>: A name for the operation (optional).
* <b>`filters`</b>: Alias for filter.


#### Returns:

A `Tensor`. Has the same type as `filter`.

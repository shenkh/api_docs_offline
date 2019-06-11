<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.depthwise_conv2d_backprop_input" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.depthwise_conv2d_backprop_input

Computes the gradients of depthwise convolution with respect to the input.

### Aliases:

* `tf.compat.v1.nn.depthwise_conv2d_backprop_input`
* `tf.compat.v1.nn.depthwise_conv2d_native_backprop_input`
* `tf.compat.v2.nn.depthwise_conv2d_backprop_input`
* `tf.nn.depthwise_conv2d_backprop_input`

``` python
tf.nn.depthwise_conv2d_backprop_input(
    input_sizes,
    filter,
    out_backprop,
    strides,
    padding,
    data_format='NHWC',
    dilations=[1, 1, 1, 1],
    name=None
)
```



Defined in generated file: `python/ops/gen_nn_ops.py`.

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`input_sizes`</b>: A `Tensor` of type `int32`.
  An integer vector representing the shape of `input`, based
  on `data_format`.  For example, if `data_format` is 'NHWC' then
   `input` is a 4-D `[batch, height, width, channels]` tensor.
* <b>`filter`</b>: A `Tensor`. Must be one of the following types: `half`, `bfloat16`, `float32`, `float64`.
  4-D with shape
  `[filter_height, filter_width, in_channels, depthwise_multiplier]`.
* <b>`out_backprop`</b>: A `Tensor`. Must have the same type as `filter`.
  4-D with shape  based on `data_format`.
  For example, if `data_format` is 'NHWC' then
  out_backprop shape is `[batch, out_height, out_width, out_channels]`.
  Gradients w.r.t. the output of the convolution.
* <b>`strides`</b>: A list of `ints`.
  The stride of the sliding window for each dimension of the input
  of the convolution.
* <b>`padding`</b>: A `string` from: `"SAME", "VALID"`.
  The type of padding algorithm to use.
* <b>`data_format`</b>: An optional `string` from: `"NHWC", "NCHW"`. Defaults to `"NHWC"`.
  Specify the data format of the input and output data. With the
  default format "NHWC", the data is stored in the order of:
      [batch, height, width, channels].
  Alternatively, the format could be "NCHW", the data storage order of:
      [batch, channels, height, width].
* <b>`dilations`</b>: An optional list of `ints`. Defaults to `[1, 1, 1, 1]`.
  1-D tensor of length 4.  The dilation factor for each dimension of
  `input`. If set to k > 1, there will be k-1 skipped cells between each filter
  element on that dimension. The dimension order is determined by the value of
  `data_format`, see above for details. Dilations in the batch and depth
  dimensions must be 1.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `filter`.

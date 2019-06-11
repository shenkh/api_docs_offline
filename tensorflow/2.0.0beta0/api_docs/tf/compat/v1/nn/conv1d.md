<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.nn.conv1d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.nn.conv1d

Computes a 1-D convolution given 3-D input and filter tensors. (deprecated argument values) (deprecated argument values)

``` python
tf.compat.v1.nn.conv1d(
    value=None,
    filters=None,
    stride=None,
    padding=None,
    use_cudnn_on_gpu=None,
    data_format=None,
    name=None,
    input=None,
    dilations=None
)
```



Defined in [`python/ops/nn_ops.py`](/code/stable/tensorflow/python/ops/nn_ops.py).

<!-- Placeholder for "Used in" -->

Warning: SOME ARGUMENT VALUES ARE DEPRECATED: `(data_format='NCHW')`. They will be removed in a future version.
Instructions for updating:
`NCHW` for data_format is deprecated, use `NCW` instead

Warning: SOME ARGUMENT VALUES ARE DEPRECATED: `(data_format='NHWC')`. They will be removed in a future version.
Instructions for updating:
`NHWC` for data_format is deprecated, use `NWC` instead

Given an input tensor of shape
  [batch, in_width, in_channels]
if data_format is "NWC", or
  [batch, in_channels, in_width]
if data_format is "NCW",
and a filter / kernel tensor of shape
[filter_width, in_channels, out_channels], this op reshapes
the arguments to pass them to conv2d to perform the equivalent
convolution operation.

Internally, this op reshapes the input tensors and invokes <a href="../../../../tf/nn/conv2d.md"><code>tf.nn.conv2d</code></a>.
For example, if `data_format` does not start with "NC", a tensor of shape
  [batch, in_width, in_channels]
is reshaped to
  [batch, 1, in_width, in_channels],
and the filter is reshaped to
  [1, filter_width, in_channels, out_channels].
The result is then reshaped back to
  [batch, out_width, out_channels]
\(where out_width is a function of the stride and padding as in conv2d\) and
returned to the caller.

#### Args:


* <b>`value`</b>: A 3D `Tensor`.  Must be of type `float16`, `float32`, or `float64`.
* <b>`filters`</b>: A 3D `Tensor`.  Must have the same type as `value`.
* <b>`stride`</b>: An int or list of `ints` that has length `1` or `3`.  The number of
  entries by which the filter is moved right at each step.
* <b>`padding`</b>: 'SAME' or 'VALID'
* <b>`use_cudnn_on_gpu`</b>: An optional `bool`.  Defaults to `True`.
* <b>`data_format`</b>: An optional `string` from `"NWC", "NCW"`.  Defaults to `"NWC"`,
  the data is stored in the order of [batch, in_width, in_channels].  The
  `"NCW"` format stores data as [batch, in_channels, in_width].
* <b>`name`</b>: A name for the operation (optional).
* <b>`input`</b>: Alias for value.
* <b>`dilations`</b>: An int or list of `ints` that has length `1` or `3` which
  defaults to 1. The dilation factor for each dimension of input. If set to
  k > 1, there will be k-1 skipped cells between each filter element on that
  dimension. Dilations in the batch and depth dimensions must be 1.


#### Returns:

A `Tensor`.  Has the same type as input.



#### Raises:


* <b>`ValueError`</b>: if `data_format` is invalid.
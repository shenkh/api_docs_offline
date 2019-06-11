<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.nn.conv3d_backprop_filter" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.nn.conv3d_backprop_filter

Computes the gradients of 3-D convolution with respect to the filter.

### Aliases:

* `tf.compat.v1.nn.conv3d_backprop_filter`
* `tf.compat.v1.nn.conv3d_backprop_filter_v2`

``` python
tf.compat.v1.nn.conv3d_backprop_filter(
    input,
    filter_sizes,
    out_backprop,
    strides,
    padding,
    data_format='NDHWC',
    dilations=[1, 1, 1, 1, 1],
    name=None
)
```



Defined in generated file: `python/ops/gen_nn_ops.py`.

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`input`</b>: A `Tensor`. Must be one of the following types: `half`, `bfloat16`, `float32`, `float64`.
  Shape `[batch, depth, rows, cols, in_channels]`.
* <b>`filter_sizes`</b>: A `Tensor` of type `int32`.
  An integer vector representing the tensor shape of `filter`,
  where `filter` is a 5-D
  `[filter_depth, filter_height, filter_width, in_channels, out_channels]`
  tensor.
* <b>`out_backprop`</b>: A `Tensor`. Must have the same type as `input`.
  Backprop signal of shape `[batch, out_depth, out_rows, out_cols,
  out_channels]`.
* <b>`strides`</b>: A list of `ints` that has length `>= 5`.
  1-D tensor of length 5. The stride of the sliding window for each
  dimension of `input`. Must have `strides[0] = strides[4] = 1`.
* <b>`padding`</b>: A `string` from: `"SAME", "VALID"`.
  The type of padding algorithm to use.
* <b>`data_format`</b>: An optional `string` from: `"NDHWC", "NCDHW"`. Defaults to `"NDHWC"`.
  The data format of the input and output data. With the
  default format "NDHWC", the data is stored in the order of:
      [batch, in_depth, in_height, in_width, in_channels].
  Alternatively, the format could be "NCDHW", the data storage order is:
      [batch, in_channels, in_depth, in_height, in_width].
* <b>`dilations`</b>: An optional list of `ints`. Defaults to `[1, 1, 1, 1, 1]`.
  1-D tensor of length 5.  The dilation factor for each dimension of
  `input`. If set to k > 1, there will be k-1 skipped cells between each
  filter element on that dimension. The dimension order is determined by the
  value of `data_format`, see above for details. Dilations in the batch and
  depth dimensions must be 1.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.

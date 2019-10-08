<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.avg_pool" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.avg_pool

``` python
tf.nn.avg_pool(
    input,
    ksize,
    strides,
    padding,
    data_format=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/nn_ops.py`](/code/stable/tensorflow/python/ops/nn_ops.py).

Performs the avg pooling on the input.

Each entry in `output` is the mean of the corresponding size `ksize`
window in `value`.

#### Args:

* <b>`input`</b>:  Tensor of rank N+2, of shape `[batch_size] + input_spatial_shape +
    [num_channels]` if `data_format` does not start with "NC" (default), or
    `[batch_size, num_channels] + input_spatial_shape` if data_format starts
    with "NC". Pooling happens over the spatial dimensions only.
* <b>`ksize`</b>: An int or list of `ints` that has length `1`, `N` or `N+2`. The size
    of the window for each dimension of the input tensor.
* <b>`strides`</b>: An int or list of `ints` that has length `1`, `N` or `N+2`. The
    stride of the sliding window for each dimension of the input tensor.
* <b>`padding`</b>: A string, either `'VALID'` or `'SAME'`. The padding algorithm. See
    the "returns" section of <a href="../../tf/nn/convolution.md"><code>tf.nn.convolution</code></a> for details.
* <b>`data_format`</b>: A string. Specifies the channel dimension. For N=1 it can be
    either "NWC" (default) or "NCW", for N=2 it can be either "NHWC" (default)
    or "NCHW" and for N=3 either "NDHWC" (default) or "NCDHW".
* <b>`name`</b>: Optional name for the operation.


#### Returns:

A `Tensor` of format specified by `data_format`.
The average pooled output tensor.
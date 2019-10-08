<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.avg_pool1d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.avg_pool1d

``` python
tf.nn.avg_pool1d(
    input,
    ksize,
    strides,
    padding,
    data_format='NWC',
    name=None
)
```



Defined in [`tensorflow/python/ops/nn_ops.py`](/code/stable/tensorflow/python/ops/nn_ops.py).

Performs the average pooling on the input.

Each entry in `output` is the mean of the corresponding size `ksize`
window in `value`.

Note internally this op reshapes and uses the underlying 2d operation.

#### Args:

* <b>`input`</b>: A 3-D `Tensor` of the format specified by `data_format`.
* <b>`ksize`</b>: An int or list of `ints` that has length `1` or `3`. The size of the
    window for each dimension of the input tensor.
* <b>`strides`</b>: An int or list of `ints` that has length `1` or `3`. The stride of
    the sliding window for each dimension of the input tensor.
* <b>`padding`</b>: A string, either `'VALID'` or `'SAME'`. The padding algorithm. See
    the "returns" section of <a href="../../tf/nn/convolution.md"><code>tf.nn.convolution</code></a> for details.
* <b>`data_format`</b>: An optional string from: "NWC", "NCW". Defaults to "NWC".
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of format specified by `data_format`.
The max pooled output tensor.
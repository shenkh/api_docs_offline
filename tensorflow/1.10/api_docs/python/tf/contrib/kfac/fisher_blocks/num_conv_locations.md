<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.fisher_blocks.num_conv_locations" />
</div>

# tf.contrib.kfac.fisher_blocks.num_conv_locations

``` python
tf.contrib.kfac.fisher_blocks.num_conv_locations(
    input_shape,
    strides
)
```



Defined in [`tensorflow/contrib/kfac/python/ops/fisher_blocks.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/fisher_blocks.py).

Returns the number of spatial locations a 2D Conv kernel is applied to.

#### Args:

* <b>`input_shape`</b>: List of ints representing shape of inputs to
    tf.nn.convolution().
* <b>`strides`</b>: List of ints representing strides along spatial dimensions as
    passed in to tf.nn.convolution().


#### Returns:

A scalar |T| denoting the number of spatial locations for the Conv layer.
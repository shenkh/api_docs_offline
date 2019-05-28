<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.with_same_shape" />
</div>

# tf.contrib.framework.with_same_shape

``` python
tf.contrib.framework.with_same_shape(
    expected_tensor,
    tensor
)
```



Defined in [`tensorflow/contrib/framework/python/framework/tensor_util.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/framework/tensor_util.py).

See the guide: [Framework (contrib)](../../../../../api_guides/python/contrib.framework.md)

Assert tensors are the same shape, from the same graph.

#### Args:

* <b>`expected_tensor`</b>: Tensor with expected shape.
* <b>`tensor`</b>: Tensor of actual values.

#### Returns:

The original tensor argument, possibly with assert ops added.
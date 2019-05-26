<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.with_shape" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.framework.with_shape

``` python
tf.contrib.framework.with_shape(
    expected_shape,
    tensor
)
```



Defined in [`tensorflow/contrib/framework/python/framework/tensor_util.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/framework/tensor_util.py).

Asserts tensor has expected shape.

If tensor shape and expected_shape, are fully defined, assert they match.
Otherwise, add assert op that will validate the shape when tensor is
evaluated, and set shape on tensor.

#### Args:

* <b>`expected_shape`</b>: Expected shape to assert, as a 1D array of ints, or tensor
      of same.
* <b>`tensor`</b>: Tensor whose shape we're validating.

#### Returns:

tensor, perhaps with a dependent assert operation.

#### Raises:

* <b>`ValueError`</b>: if tensor has an invalid shape.
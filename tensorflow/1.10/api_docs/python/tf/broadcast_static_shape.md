<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.broadcast_static_shape" />
</div>

# tf.broadcast_static_shape

``` python
tf.broadcast_static_shape(
    shape_x,
    shape_y
)
```



Defined in [`tensorflow/python/ops/array_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/array_ops.py).

See the guide: [Tensor Transformations > Shapes and Shaping](../../../api_guides/python/array_ops.md#Shapes_and_Shaping)

Returns the broadcasted static shape between `shape_x` and `shape_y`.

#### Args:

* <b>`shape_x`</b>: A `TensorShape`
* <b>`shape_y`</b>: A `TensorShape`


#### Returns:

A `TensorShape` representing the broadcasted shape.


#### Raises:

* <b>`ValueError`</b>: If the two shapes can not be broadcasted.
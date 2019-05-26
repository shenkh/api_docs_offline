<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.broadcast_dynamic_shape" />
<meta itemprop="path" content="Stable" />
</div>

# tf.broadcast_dynamic_shape

``` python
tf.broadcast_dynamic_shape(
    shape_x,
    shape_y
)
```



Defined in [`tensorflow/python/ops/array_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/array_ops.py).

Returns the broadcasted dynamic shape between `shape_x` and `shape_y`.

#### Args:

* <b>`shape_x`</b>: A rank 1 integer `Tensor`, representing the shape of x.
* <b>`shape_y`</b>: A rank 1 integer `Tensor`, representing the shape of y.


#### Returns:

A rank 1 integer `Tensor` representing the broadcasted shape.
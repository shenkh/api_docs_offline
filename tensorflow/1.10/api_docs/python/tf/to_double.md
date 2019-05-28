<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.to_double" />
</div>

# tf.to_double

``` python
tf.to_double(
    x,
    name='ToDouble'
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guide: [Tensor Transformations > Casting](../../../api_guides/python/array_ops.md#Casting)

Casts a tensor to type `float64`.

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` with same shape as `x` with type `float64`.


#### Raises:

* <b>`TypeError`</b>: If `x` cannot be cast to the `float64`.
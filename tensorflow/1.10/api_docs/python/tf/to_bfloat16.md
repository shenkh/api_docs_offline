<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.to_bfloat16" />
</div>

# tf.to_bfloat16

``` python
tf.to_bfloat16(
    x,
    name='ToBFloat16'
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guide: [Tensor Transformations > Casting](../../../api_guides/python/array_ops.md#Casting)

Casts a tensor to type `bfloat16`.

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` with same shape as `x` with type `bfloat16`.


#### Raises:

* <b>`TypeError`</b>: If `x` cannot be cast to the `bfloat16`.
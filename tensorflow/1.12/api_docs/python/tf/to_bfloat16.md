<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.to_bfloat16" />
<meta itemprop="path" content="Stable" />
</div>

# tf.to_bfloat16

``` python
tf.to_bfloat16(
    x,
    name='ToBFloat16'
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

Casts a tensor to type `bfloat16`.

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor` or `IndexedSlices`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` or `IndexedSlices` with same shape as `x` with
type `bfloat16`.


#### Raises:

* <b>`TypeError`</b>: If `x` cannot be cast to the `bfloat16`.
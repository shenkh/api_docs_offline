<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.to_int64" />
<meta itemprop="path" content="Stable" />
</div>

# tf.to_int64

``` python
tf.to_int64(
    x,
    name='ToInt64'
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

Casts a tensor to type `int64`.

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor` or `IndexedSlices`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` or `IndexedSlices` with same shape as `x` with
type `int64`.


#### Raises:

* <b>`TypeError`</b>: If `x` cannot be cast to the `int64`.
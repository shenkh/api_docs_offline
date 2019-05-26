<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.to_complex128" />
<meta itemprop="path" content="Stable" />
</div>

# tf.to_complex128

``` python
tf.to_complex128(
    x,
    name='ToComplex128'
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

Casts a tensor to type `complex128`.

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor` or `IndexedSlices`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` or `IndexedSlices` with same shape as `x` with
type `complex128`.


#### Raises:

* <b>`TypeError`</b>: If `x` cannot be cast to the `complex128`.
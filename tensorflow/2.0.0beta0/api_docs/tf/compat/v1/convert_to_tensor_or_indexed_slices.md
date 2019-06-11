<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.convert_to_tensor_or_indexed_slices" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.convert_to_tensor_or_indexed_slices

Converts the given object to a `Tensor` or an `IndexedSlices`.

``` python
tf.compat.v1.convert_to_tensor_or_indexed_slices(
    value,
    dtype=None,
    name=None
)
```



Defined in [`python/framework/indexed_slices.py`](/code/stable/tensorflow/python/framework/indexed_slices.py).

<!-- Placeholder for "Used in" -->

If `value` is an `IndexedSlices` or `SparseTensor` it is returned
unmodified. Otherwise, it is converted to a `Tensor` using
`convert_to_tensor()`.

#### Args:


* <b>`value`</b>: An `IndexedSlices`, `SparseTensor`, or an object that can be consumed
  by `convert_to_tensor()`.
* <b>`dtype`</b>: (Optional.) The required `DType` of the returned `Tensor` or
  `IndexedSlices`.
* <b>`name`</b>: (Optional.) A name to use if a new `Tensor` is created.


#### Returns:

A `Tensor`, `IndexedSlices`, or `SparseTensor` based on `value`.



#### Raises:


* <b>`ValueError`</b>: If `dtype` does not match the element type of `value`.
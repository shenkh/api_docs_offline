<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.ragged.constant" />
<meta itemprop="path" content="Stable" />
</div>

# tf.ragged.constant

Constructs a constant RaggedTensor from a nested Python list.

### Aliases:

* `tf.compat.v1.ragged.constant`
* `tf.compat.v2.ragged.constant`
* `tf.ragged.constant`

``` python
tf.ragged.constant(
    pylist,
    dtype=None,
    ragged_rank=None,
    inner_shape=None,
    name=None,
    row_splits_dtype=tf.dtypes.int64
)
```



Defined in [`python/ops/ragged/ragged_factory_ops.py`](/code/stable/tensorflow/python/ops/ragged/ragged_factory_ops.py).

<!-- Placeholder for "Used in" -->


#### Example:



```python
>>> ragged.constant([[1, 2], [3], [4, 5, 6]]).eval()
RaggedTensorValue(values=[1, 2, 3, 4, 5, 6], splits=[0, 2, 3, 6])
```

All scalar values in `pylist` must have the same nesting depth `K`, and the
returned `RaggedTensor` will have rank `K`.  If `pylist` contains no scalar
values, then `K` is one greater than the maximum depth of empty lists in
`pylist`.  All scalar values in `pylist` must be compatible with `dtype`.

#### Args:


* <b>`pylist`</b>: A nested `list`, `tuple` or `np.ndarray`.  Any nested element that
  is not a `list`, `tuple` or `np.ndarray` must be a scalar value
  compatible with `dtype`.
* <b>`dtype`</b>: The type of elements for the returned `RaggedTensor`.  If not
  specified, then a default is chosen based on the scalar values in
  `pylist`.
* <b>`ragged_rank`</b>: An integer specifying the ragged rank of the returned
  `RaggedTensor`.  Must be nonnegative and less than `K`. Defaults to
  `max(0, K - 1)` if `inner_shape` is not specified.  Defaults to `max(0, K
  - 1 - len(inner_shape))` if `inner_shape` is specified.
* <b>`inner_shape`</b>: A tuple of integers specifying the shape for individual inner
  values in the returned `RaggedTensor`.  Defaults to `()` if `ragged_rank`
  is not specified.  If `ragged_rank` is specified, then a default is chosen
  based on the contents of `pylist`.
* <b>`name`</b>: A name prefix for the returned tensor (optional).
* <b>`row_splits_dtype`</b>: data type for the constructed `RaggedTensor`'s row_splits.
  One of <a href="../../tf.md#int32"><code>tf.int32</code></a> or <a href="../../tf.md#int64"><code>tf.int64</code></a>.


#### Returns:

A potentially ragged tensor with rank `K` and the specified `ragged_rank`,
containing the values from `pylist`.



#### Raises:


* <b>`ValueError`</b>: If the scalar values in `pylist` have inconsistent nesting
  depth; or if ragged_rank or inner_shape are incompatible with `pylist`.
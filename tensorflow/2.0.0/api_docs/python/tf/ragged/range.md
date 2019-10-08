<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.ragged.range" />
<meta itemprop="path" content="Stable" />
</div>

# tf.ragged.range

``` python
tf.ragged.range(
    starts,
    limits=None,
    deltas=1,
    dtype=None,
    name=None,
    row_splits_dtype=tf.dtypes.int64
)
```



Defined in [`tensorflow/python/ops/ragged/ragged_math_ops.py`](/code/stable/tensorflow/python/ops/ragged/ragged_math_ops.py).

Returns a `RaggedTensor` containing the specified sequences of numbers.

Each row of the returned `RaggedTensor` contains a single sequence:

```python
ragged.range(starts, limits, deltas)[i] ==
    tf.range(starts[i], limits[i], deltas[i])
```

If `start[i] < limits[i] and deltas[i] > 0`, then `output[i]` will be an
empty list.  Similarly, if `start[i] > limits[i] and deltas[i] < 0`, then
`output[i]` will be an empty list.  This behavior is consistent with the
Python `range` function, but differs from the <a href="../../tf/range.md"><code>tf.range</code></a> op, which returns
an error for these cases.

Examples:

```python
>>> ragged.range([3, 5, 2]).eval().tolist()
[[0, 1, 2], [0, 1, 2, 3, 4], [0, 1]]
>>> ragged.range([0, 5, 8], [3, 3, 12]).eval().tolist()
[[0, 1, 2], [], [8, 9, 10, 11]]
>>> ragged.range([0, 5, 8], [3, 3, 12], 2).eval().tolist()
[[0, 2], [], [8, 10]]
```

The input tensors `starts`, `limits`, and `deltas` may be scalars or vectors.
The vector inputs must all have the same size.  Scalar inputs are broadcast
to match the size of the vector inputs.

#### Args:

* <b>`starts`</b>: Vector or scalar `Tensor`.  Specifies the first entry for each range
    if `limits` is not `None`; otherwise, specifies the range limits, and the
    first entries default to `0`.
* <b>`limits`</b>: Vector or scalar `Tensor`.  Specifies the exclusive upper limits for
    each range.
* <b>`deltas`</b>: Vector or scalar `Tensor`.  Specifies the increment for each range.
    Defaults to `1`.
* <b>`dtype`</b>: The type of the elements of the resulting tensor.  If not specified,
    then a value is chosen based on the other args.
* <b>`name`</b>: A name for the operation.
* <b>`row_splits_dtype`</b>: `dtype` for the returned `RaggedTensor`'s `row_splits`
    tensor.  One of <a href="../../tf/dtypes.md#int32"><code>tf.int32</code></a> or <a href="../../tf/dtypes.md#int64"><code>tf.int64</code></a>.


#### Returns:

A `RaggedTensor` of type `dtype` with `ragged_rank=1`.
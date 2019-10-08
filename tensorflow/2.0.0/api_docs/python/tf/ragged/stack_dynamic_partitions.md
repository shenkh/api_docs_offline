<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.ragged.stack_dynamic_partitions" />
<meta itemprop="path" content="Stable" />
</div>

# tf.ragged.stack_dynamic_partitions

``` python
tf.ragged.stack_dynamic_partitions(
    data,
    partitions,
    num_partitions,
    name=None
)
```



Defined in [`tensorflow/python/ops/ragged/ragged_array_ops.py`](/code/stable/tensorflow/python/ops/ragged/ragged_array_ops.py).

Stacks dynamic partitions of a Tensor or RaggedTensor.

Returns a RaggedTensor `output` with `num_partitions` rows, where the row
`output[i]` is formed by stacking all slices `data[j1...jN]` such that
`partitions[j1...jN] = i`.  Slices of `data` are stacked in row-major
order.

If `num_partitions` is an `int` (not a `Tensor`), then this is equivalent to
`tf.ragged.stack(tf.dynamic_partition(data, partitions, num_partitions))`.

####Example:
  ```python
  >>> data           = ['a', 'b', 'c', 'd', 'e']
  >>> partitions     = [  3,   0,   2,   2,   3]
  >>> num_partitions = 5
  >>> tf.ragged.stack_dynamic_partitions(data, partitions, num_partitions)
  <RaggedTensor [['b'], [], ['c', 'd'], ['a', 'e'], []]>
  ```

#### Args:

* <b>`data`</b>: A `Tensor` or `RaggedTensor` containing the values to stack.
* <b>`partitions`</b>: An `int32` or `int64` `Tensor` or `RaggedTensor` specifying the
    partition that each slice of `data` should be added to.
    `partitions.shape` must be a prefix of `data.shape`.  Values must be
    greater than or equal to zero, and less than `num_partitions`.
    `partitions` is not required to be sorted.
* <b>`num_partitions`</b>: An `int32` or `int64` scalar specifying the number of
    partitions to output.  This determines the number of rows in `output`.
* <b>`name`</b>: A name prefix for the returned tensor (optional).


#### Returns:

A `RaggedTensor` containing the stacked partitions.  The returned tensor
has the same dtype as `data`, and its shape is
`[num_partitions, (D)] + data.shape[partitions.rank:]`, where `(D)` is a
ragged dimension whose length is the number of data slices stacked for
each `partition`.
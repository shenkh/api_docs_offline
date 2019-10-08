<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.ragged.stack" />
<meta itemprop="path" content="Stable" />
</div>

# tf.ragged.stack

``` python
tf.ragged.stack(
    values,
    axis=0,
    name=None
)
```



Defined in [`tensorflow/python/ops/ragged/ragged_concat_ops.py`](/code/stable/tensorflow/python/ops/ragged/ragged_concat_ops.py).

Stacks a list of rank-`R` tensors into one rank-`(R+1)` `RaggedTensor`.

Given a list of tensors or ragged tensors with the same rank `R`
(`R >= axis`), returns a rank-`R+1` `RaggedTensor` `result` such that
`result[i0...iaxis]` is `[value[i0...iaxis] for value in values]`.

#### Example:
  ```python
  >>> t1 = tf.ragged.constant([[1, 2], [3, 4, 5]])
  >>> t2 = tf.ragged.constant([[6], [7, 8, 9]])
  >>> tf.ragged.stack([t1, t2], axis=0)
  [[[1, 2], [3, 4, 5]], [[6], [7, 9, 0]]]
  >>> tf.ragged.stack([t1, t2], axis=1)
  [[[1, 2], [6]], [[3, 4, 5], [7, 8, 9]]]
  ```

#### Args:

* <b>`values`</b>: A list of <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> or <a href="../../tf/RaggedTensor.md"><code>tf.RaggedTensor</code></a>.  May not be empty. All
    `values` must have the same rank and the same dtype; but unlike
    <a href="../../tf/stack.md"><code>tf.stack</code></a>, they can have arbitrary dimension sizes.
* <b>`axis`</b>: A python integer, indicating the dimension along which to stack.
    (Note: Unlike <a href="../../tf/stack.md"><code>tf.stack</code></a>, the `axis` parameter must be statically known.)
    Negative values are supported only if the rank of at least one
    `values` value is statically known.
* <b>`name`</b>: A name prefix for the returned tensor (optional).


#### Returns:

A `RaggedTensor` with rank `R+1`.
`result.ragged_rank=1+max(axis, max(rt.ragged_rank for rt in values]))`.


#### Raises:

* <b>`ValueError`</b>: If `values` is empty, if `axis` is out of bounds or if
    the input tensors have different ranks.
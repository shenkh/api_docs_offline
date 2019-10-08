<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.ragged.row_splits_to_segment_ids" />
<meta itemprop="path" content="Stable" />
</div>

# tf.ragged.row_splits_to_segment_ids

``` python
tf.ragged.row_splits_to_segment_ids(
    splits,
    name=None,
    out_type=None
)
```



Defined in [`tensorflow/python/ops/ragged/segment_id_ops.py`](/code/stable/tensorflow/python/ops/ragged/segment_id_ops.py).

Generates the segmentation corresponding to a RaggedTensor `row_splits`.

Returns an integer vector `segment_ids`, where `segment_ids[i] == j` if
`splits[j] <= i < splits[j+1]`.  Example:

```python
>>> ragged.row_splits_to_segment_ids([0, 3, 3, 5, 6, 9]).eval()
[ 0 0 0 2 2 3 4 4 4 ]
```

#### Args:

* <b>`splits`</b>: A sorted 1-D integer Tensor.  `splits[0]` must be zero.
* <b>`name`</b>: A name prefix for the returned tensor (optional).
* <b>`out_type`</b>: The dtype for the return value.  Defaults to `splits.dtype`,
    or <a href="../../tf/dtypes.md#int64"><code>tf.int64</code></a> if `splits` does not have a dtype.


#### Returns:

A sorted 1-D integer Tensor, with `shape=[splits[-1]]`


#### Raises:

* <b>`ValueError`</b>: If `splits` is invalid.
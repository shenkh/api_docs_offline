<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.metrics.precision_at_top_k" />
<meta itemprop="path" content="Stable" />
</div>

# tf.metrics.precision_at_top_k

``` python
tf.metrics.precision_at_top_k(
    labels,
    predictions_idx,
    k=None,
    class_id=None,
    weights=None,
    metrics_collections=None,
    updates_collections=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/metrics_impl.py`](/code/stable/tensorflow/python/ops/metrics_impl.py).

Computes precision@k of the predictions with respect to sparse labels.

Differs from `sparse_precision_at_k` in that predictions must be in the form
of top `k` class indices, whereas `sparse_precision_at_k` expects logits.
Refer to `sparse_precision_at_k` for more details.

#### Args:

* <b>`labels`</b>: `int64` `Tensor` or `SparseTensor` with shape
    [D1, ... DN, num_labels] or [D1, ... DN], where the latter implies
    num_labels=1. N >= 1 and num_labels is the number of target classes for
    the associated prediction. Commonly, N=1 and `labels` has shape
    [batch_size, num_labels]. [D1, ... DN] must match `predictions`. Values
    should be in range [0, num_classes), where num_classes is the last
    dimension of `predictions`. Values outside this range are ignored.
* <b>`predictions_idx`</b>: Integer `Tensor` with shape [D1, ... DN, k] where
    N >= 1. Commonly, N=1 and predictions has shape [batch size, k].
    The final dimension contains the top `k` predicted class indices.
    [D1, ... DN] must match `labels`.
* <b>`k`</b>: Integer, k for @k metric. Only used for the default op name.
* <b>`class_id`</b>: Integer class ID for which we want binary metrics. This should be
    in range [0, num_classes], where num_classes is the last dimension of
    `predictions`. If `class_id` is outside this range, the method returns
    NAN.
* <b>`weights`</b>: `Tensor` whose rank is either 0, or n-1, where n is the rank of
    `labels`. If the latter, it must be broadcastable to `labels` (i.e., all
    dimensions must be either `1`, or the same as the corresponding `labels`
    dimension).
* <b>`metrics_collections`</b>: An optional list of collections that values should
    be added to.
* <b>`updates_collections`</b>: An optional list of collections that updates should
    be added to.
* <b>`name`</b>: Name of new update operation, and namespace for other dependent ops.


#### Returns:

* <b>`precision`</b>: Scalar `float64` `Tensor` with the value of `true_positives`
    divided by the sum of `true_positives` and `false_positives`.
* <b>`update_op`</b>: `Operation` that increments `true_positives` and
    `false_positives` variables appropriately, and whose value matches
    `precision`.


#### Raises:

* <b>`ValueError`</b>: If `weights` is not `None` and its shape doesn't match
    `predictions`, or if either `metrics_collections` or `updates_collections`
    are not a list or tuple.
* <b>`RuntimeError`</b>: If eager execution is enabled.
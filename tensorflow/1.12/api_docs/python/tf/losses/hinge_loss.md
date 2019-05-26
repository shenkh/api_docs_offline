<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.hinge_loss" />
<meta itemprop="path" content="Stable" />
</div>

# tf.losses.hinge_loss

``` python
tf.losses.hinge_loss(
    labels,
    logits,
    weights=1.0,
    scope=None,
    loss_collection=tf.GraphKeys.LOSSES,
    reduction=Reduction.SUM_BY_NONZERO_WEIGHTS
)
```



Defined in [`tensorflow/python/ops/losses/losses_impl.py`](/code/stable/tensorflow/python/ops/losses/losses_impl.py).

Adds a hinge loss to the training procedure.

#### Args:

* <b>`labels`</b>: The ground truth output tensor. Its shape should match the shape of
    logits. The values of the tensor are expected to be 0.0 or 1.0. Internally
    the {0,1} labels are converted to {-1,1} when calculating the hinge loss.
* <b>`logits`</b>: The logits, a float tensor. Note that logits are assumed to be
    unbounded and 0-centered. A value > 0 (resp. < 0) is considered a positive
    (resp. negative) binary prediction.
* <b>`weights`</b>: Optional `Tensor` whose rank is either 0, or the same rank as
    `labels`, and must be broadcastable to `labels` (i.e., all dimensions must
    be either `1`, or the same as the corresponding `losses` dimension).
* <b>`scope`</b>: The scope for the operations performed in computing the loss.
* <b>`loss_collection`</b>: collection to which the loss will be added.
* <b>`reduction`</b>: Type of reduction to apply to loss.


#### Returns:

Weighted loss float `Tensor`. If `reduction` is `NONE`, this has the same
shape as `labels`; otherwise, it is scalar.


#### Raises:

* <b>`ValueError`</b>: If the shapes of `logits` and `labels` don't match or
    if `labels` or `logits` is None.



#### Eager Compatibility
The `loss_collection` argument is ignored when executing eagerly. Consider
holding on to the return value or collecting losses via a <a href="../../tf/keras/models/Model.md"><code>tf.keras.Model</code></a>.


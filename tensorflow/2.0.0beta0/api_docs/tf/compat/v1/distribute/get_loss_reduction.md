<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.distribute.get_loss_reduction" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.distribute.get_loss_reduction

<a href="../../../../tf/distribute/ReduceOp.md"><code>tf.distribute.ReduceOp</code></a> corresponding to the last loss reduction.

``` python
tf.compat.v1.distribute.get_loss_reduction()
```



Defined in [`python/distribute/distribute_lib.py`](/code/stable/tensorflow/python/distribute/distribute_lib.py).

<!-- Placeholder for "Used in" -->

This is used to decide whether loss should be scaled in optimizer (used only
for estimator + v1 optimizer use case).

#### Returns:

<a href="../../../../tf/distribute/ReduceOp.md"><code>tf.distribute.ReduceOp</code></a> corresponding to the last loss reduction for
estimator and v1 optimizer use case. <a href="../../../../tf/distribute/ReduceOp.md#SUM"><code>tf.distribute.ReduceOp.SUM</code></a> otherwise.

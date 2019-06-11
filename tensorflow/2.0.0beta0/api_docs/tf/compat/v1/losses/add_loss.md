<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.losses.add_loss" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.losses.add_loss

Adds a externally defined loss to the collection of losses.

``` python
tf.compat.v1.losses.add_loss(
    loss,
    loss_collection=tf.GraphKeys.LOSSES
)
```



Defined in [`python/ops/losses/util.py`](/code/stable/tensorflow/python/ops/losses/util.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`loss`</b>: A loss `Tensor`.
* <b>`loss_collection`</b>: Optional collection to add the loss to.
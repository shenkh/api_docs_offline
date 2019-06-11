<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.losses.get_losses" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.losses.get_losses

Gets the list of losses from the loss_collection.

``` python
tf.compat.v1.losses.get_losses(
    scope=None,
    loss_collection=tf.GraphKeys.LOSSES
)
```



Defined in [`python/ops/losses/util.py`](/code/stable/tensorflow/python/ops/losses/util.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`scope`</b>: An optional scope name for filtering the losses to return.
* <b>`loss_collection`</b>: Optional losses collection.


#### Returns:

a list of loss tensors.

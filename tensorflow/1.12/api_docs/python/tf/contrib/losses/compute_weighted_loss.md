<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.losses.compute_weighted_loss" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.losses.compute_weighted_loss

``` python
tf.contrib.losses.compute_weighted_loss(
    losses,
    weights=1.0,
    scope=None
)
```



Defined in [`tensorflow/contrib/losses/python/losses/loss_ops.py`](/code/stable/tensorflow/contrib/losses/python/losses/loss_ops.py).

Computes the weighted loss. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed after 2016-12-30.
Instructions for updating:
Use tf.losses.compute_weighted_loss instead.

#### Args:

* <b>`losses`</b>: A tensor of size [batch_size, d1, ... dN].
* <b>`weights`</b>: A tensor of size [1] or [batch_size, d1, ... dK] where K < N.
* <b>`scope`</b>: the scope for the operations performed in computing the loss.


#### Returns:

A scalar `Tensor` that returns the weighted loss.


#### Raises:

* <b>`ValueError`</b>: If `weights` is `None` or the shape is not compatible with
    `losses`, or if the number of dimensions (rank) of either `losses` or
    `weights` is missing.
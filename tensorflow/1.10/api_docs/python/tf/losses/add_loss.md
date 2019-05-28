<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.add_loss" />
</div>

# tf.losses.add_loss

``` python
tf.losses.add_loss(
    loss,
    loss_collection=tf.GraphKeys.LOSSES
)
```



Defined in [`tensorflow/python/ops/losses/util.py`](https://www.tensorflow.org/code/tensorflow/python/ops/losses/util.py).

Adds a externally defined loss to the collection of losses.

#### Args:

* <b>`loss`</b>: A loss `Tensor`.
* <b>`loss_collection`</b>: Optional collection to add the loss to.
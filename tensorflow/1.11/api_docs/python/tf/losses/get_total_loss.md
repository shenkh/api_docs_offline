<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.get_total_loss" />
<meta itemprop="path" content="Stable" />
</div>

# tf.losses.get_total_loss

``` python
tf.losses.get_total_loss(
    add_regularization_losses=True,
    name='total_loss'
)
```



Defined in [`tensorflow/python/ops/losses/util.py`](https://www.tensorflow.org/code/tensorflow/python/ops/losses/util.py).

Returns a tensor whose value represents the total loss.

In particular, this adds any losses you have added with `tf.add_loss()` to
any regularization losses that have been added by regularization parameters
on layers constructors e.g. <a href="../../tf/layers.md"><code>tf.layers</code></a>. Be very sure to use this if you
are constructing a loss_op manually. Otherwise regularization arguments
on <a href="../../tf/layers.md"><code>tf.layers</code></a> methods will not function.

#### Args:

* <b>`add_regularization_losses`</b>: A boolean indicating whether or not to use the
    regularization losses in the sum.
* <b>`name`</b>: The name of the returned tensor.


#### Returns:

A `Tensor` whose value represents the total loss.


#### Raises:

* <b>`ValueError`</b>: if `losses` is not iterable.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.losses.wargs.cycle_consistency_loss" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.gan.losses.wargs.cycle_consistency_loss

``` python
tf.contrib.gan.losses.wargs.cycle_consistency_loss(
    data_x,
    reconstructed_data_x,
    data_y,
    reconstructed_data_y,
    scope=None,
    add_summaries=False
)
```



Defined in [`tensorflow/contrib/gan/python/losses/python/losses_impl.py`](https://www.tensorflow.org/code/tensorflow/contrib/gan/python/losses/python/losses_impl.py).

Defines the cycle consistency loss.

The cyclegan model has two partial models where `model_x2y` generator F maps
data set X to Y, `model_y2x` generator G maps data set Y to X. For a `data_x`
in data set X, we could reconstruct it by
* reconstructed_data_x = G(F(data_x))
Similarly
* reconstructed_data_y = F(G(data_y))

The cycle consistency loss is about the difference between data and
reconstructed data, namely
* loss_x2x = |data_x - G(F(data_x))| (L1-norm)
* loss_y2y = |data_y - F(G(data_y))| (L1-norm)
* loss = (loss_x2x + loss_y2y) / 2
where `loss` is the final result.

For the L1-norm, we follow the original implementation:
https://github.com/junyanz/CycleGAN/blob/master/models/cycle_gan_model.lua
we use L1-norm of pixel-wise error normalized by data size such that
`cycle_loss_weight` can be specified independent of image size.

See https://arxiv.org/abs/1703.10593 for more details.

#### Args:

* <b>`data_x`</b>: A `Tensor` of data X.
* <b>`reconstructed_data_x`</b>: A `Tensor` of reconstructed data X.
* <b>`data_y`</b>: A `Tensor` of data Y.
* <b>`reconstructed_data_y`</b>: A `Tensor` of reconstructed data Y.
* <b>`scope`</b>: The scope for the operations performed in computing the loss.
    Defaults to None.
* <b>`add_summaries`</b>: Whether or not to add detailed summaries for the loss.
    Defaults to False.


#### Returns:

A scalar `Tensor` of cycle consistency loss.
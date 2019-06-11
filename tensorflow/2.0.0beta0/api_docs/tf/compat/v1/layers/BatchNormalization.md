<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.layers.BatchNormalization" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="scope_name"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.compat.v1.layers.BatchNormalization

## Class `BatchNormalization`

Batch Normalization layer from http://arxiv.org/abs/1502.03167.

Inherits From: [`BatchNormalization`](../../../../tf/compat/v1/keras/layers/BatchNormalization.md), [`Layer`](../../../../tf/compat/v1/layers/Layer.md)



Defined in [`python/layers/normalization.py`](/code/stable/tensorflow/python/layers/normalization.py).

<!-- Placeholder for "Used in" -->

"Batch Normalization: Accelerating Deep Network Training by Reducing
Internal Covariate Shift"

Sergey Ioffe, Christian Szegedy

Keras APIs handle BatchNormalization updates to the moving_mean and
moving_variance as part of their `fit()` and `evaluate()` loops. However, if a
custom training loop is used with an instance of `Model`, these updates need
to be explicitly included.  Here's a simple example of how it can be done:

```python
  #`model` is an instance of `Model` with `tf.keras.layers.BatchNormalization`
  update_ops = model.get_updates_for(None) + model.get_updates_for(features)
  train_op = optimizer.minimize(loss)
  train_op = tf.group([train_op, update_ops])
```

#### Arguments:


* <b>`axis`</b>: An `int` or list of `int`, the axis or axes that should be
    normalized, typically the features axis/axes. For instance, after a
    `Conv2D` layer with `data_format="channels_first"`, set `axis=1`. If a
    list of axes is provided, each axis in `axis` will be normalized
    simultaneously. Default is `-1` which uses the last axis. Note: when
    using multi-axis batch norm, the `beta`, `gamma`, `moving_mean`, and
    `moving_variance` variables are the same rank as the input Tensor, with
    dimension size 1 in all reduced (non-axis) dimensions).
* <b>`momentum`</b>: Momentum for the moving average.
* <b>`epsilon`</b>: Small float added to variance to avoid dividing by zero.
* <b>`center`</b>: If True, add offset of `beta` to normalized tensor. If False, `beta`
  is ignored.
* <b>`scale`</b>: If True, multiply by `gamma`. If False, `gamma` is
  not used. When the next layer is linear (also e.g. `nn.relu`), this can be
  disabled since the scaling can be done by the next layer.
* <b>`beta_initializer`</b>: Initializer for the beta weight.
* <b>`gamma_initializer`</b>: Initializer for the gamma weight.
* <b>`moving_mean_initializer`</b>: Initializer for the moving mean.
* <b>`moving_variance_initializer`</b>: Initializer for the moving variance.
* <b>`beta_regularizer`</b>: Optional regularizer for the beta weight.
* <b>`gamma_regularizer`</b>: Optional regularizer for the gamma weight.
* <b>`beta_constraint`</b>: An optional projection function to be applied to the `beta`
    weight after being updated by an `Optimizer` (e.g. used to implement
    norm constraints or value constraints for layer weights). The function
    must take as input the unprojected variable and must return the
    projected variable (which must have the same shape). Constraints are
    not safe to use when doing asynchronous distributed training.
* <b>`gamma_constraint`</b>: An optional projection function to be applied to the
    `gamma` weight after being updated by an `Optimizer`.
* <b>`renorm`</b>: Whether to use Batch Renormalization
  (https://arxiv.org/abs/1702.03275). This adds extra variables during
  training. The inference is the same for either value of this parameter.
* <b>`renorm_clipping`</b>: A dictionary that may map keys 'rmax', 'rmin', 'dmax' to
  scalar `Tensors` used to clip the renorm correction. The correction
  `(r, d)` is used as `corrected_value = normalized_value * r + d`, with
  `r` clipped to [rmin, rmax], and `d` to [-dmax, dmax]. Missing rmax, rmin,
  dmax are set to inf, 0, inf, respectively.
* <b>`renorm_momentum`</b>: Momentum used to update the moving means and standard
  deviations with renorm. Unlike `momentum`, this affects training
  and should be neither too small (which would add noise) nor too large
  (which would give stale estimates). Note that `momentum` is still applied
  to get the means and variances for inference.
* <b>`fused`</b>: if `None` or `True`, use a faster, fused implementation if possible.
  If `False`, use the system recommended implementation.
* <b>`trainable`</b>: Boolean, if `True` also add variables to the graph collection
  `GraphKeys.TRAINABLE_VARIABLES` (see tf.Variable).
* <b>`virtual_batch_size`</b>: An `int`. By default, `virtual_batch_size` is `None`,
  which means batch normalization is performed across the whole batch. When
  `virtual_batch_size` is not `None`, instead perform "Ghost Batch
  Normalization", which creates virtual sub-batches which are each
  normalized separately (with shared gamma, beta, and moving statistics).
  Must divide the actual batch size during execution.
* <b>`adjustment`</b>: A function taking the `Tensor` containing the (dynamic) shape of
  the input tensor and returning a pair (scale, bias) to apply to the
  normalized values (before gamma and beta), only during training. For
  example, if axis==-1,
    `adjustment = lambda shape: (
      tf.random.uniform(shape[-1:], 0.93, 1.07),
      tf.random.uniform(shape[-1:], -0.1, 0.1))`
  will scale the normalized value by up to 7% up or down, then shift the
  result by up to 0.1 (with independent scaling and bias for each feature
  but shared across all examples), and finally apply gamma and/or beta. If
  `None`, no adjustment is applied. Cannot be specified if
  virtual_batch_size is specified.
* <b>`name`</b>: A string, the name of the layer.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    axis=-1,
    momentum=0.99,
    epsilon=0.001,
    center=True,
    scale=True,
    beta_initializer=tf.zeros_initializer(),
    gamma_initializer=tf.ones_initializer(),
    moving_mean_initializer=tf.zeros_initializer(),
    moving_variance_initializer=tf.ones_initializer(),
    beta_regularizer=None,
    gamma_regularizer=None,
    beta_constraint=None,
    gamma_constraint=None,
    renorm=False,
    renorm_clipping=None,
    renorm_momentum=0.99,
    fused=None,
    trainable=True,
    virtual_batch_size=None,
    adjustment=None,
    name=None,
    **kwargs
)
```






## Properties

<h3 id="graph"><code>graph</code></h3>

DEPRECATED FUNCTION

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Stop using this property because tf.layers layers no longer track their graph.

<h3 id="scope_name"><code>scope_name</code></h3>







<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.mixed_precision.FixedLossScaleManager" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_loss_scale"/>
<meta itemprop="property" content="update_loss_scale"/>
</div>

# tf.contrib.mixed_precision.FixedLossScaleManager

## Class `FixedLossScaleManager`

Inherits From: [`LossScaleManager`](../../../tf/contrib/mixed_precision/LossScaleManager.md)



Defined in [`tensorflow/contrib/mixed_precision/python/loss_scale_manager.py`](/code/stable/tensorflow/contrib/mixed_precision/python/loss_scale_manager.py).

Loss scale manager with a fixed loss scale.

The loss scale is not updated for the lifetime of the class.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(loss_scale)
```

Creates the fixed loss scale manager.

#### Args:

* <b>`loss_scale`</b>: A Python float. Its ideal value varies depending on models to
    run. Choosing a too small loss_scale might affect model quality; a too
    big loss_scale might cause inf or nan. There is no single right
    loss_scale to apply. There is no harm choosing a relatively big number
    as long as no nan or inf is encountered in training.


#### Raises:

* <b>`ValueError`</b>: If loss_scale is less than 1.



## Methods

<h3 id="get_loss_scale"><code>get_loss_scale</code></h3>

``` python
get_loss_scale()
```

Returns the loss scale as a scalar `float32` tensor.

<h3 id="update_loss_scale"><code>update_loss_scale</code></h3>

``` python
update_loss_scale(finite_grads)
```

Updates loss scale based on if gradients are finite in current step.

#### Args:

* <b>`finite_grads`</b>: bool scalar tensor indicating if all gradients are
    finite (i.e., not inf or nan).


#### Returns:

An op, when executed updates the loss scale. If eager execution is
enabled, does not return anything.




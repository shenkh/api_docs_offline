<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.experimental.DynamicLossScale" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="increment_period"/>
<meta itemprop="property" content="initial_loss_scale"/>
<meta itemprop="property" content="multiplier"/>
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
<meta itemprop="property" content="update"/>
</div>

# tf.train.experimental.DynamicLossScale

## Class `DynamicLossScale`

Inherits From: [`LossScale`](../../../tf/train/experimental/LossScale.md)



Defined in [`tensorflow/python/training/experimental/loss_scale.py`](/code/stable/tensorflow/python/training/experimental/loss_scale.py).

Loss scale that dynamically adjusts itself.

Dynamic loss scaling works by adjusting the loss scale as training progresses.
The goal is to keep the loss scale as high as possible without overflowing the
gradients. As long as the gradients do not overflow, raising the loss scale
never hurts.

The algorithm starts by setting the loss scale to an initial value. Every N
steps that the gradients are finite, the loss scale is increased by some
factor. However, if a NaN or Inf gradient is found, the gradients for that
step are not applied, and the loss scale is decreased by the factor. This
process tends to keep the loss scale as high as possible without gradients
overflowing.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    initial_loss_scale=(2 ** 15),
    increment_period=2000,
    multiplier=2.0
)
```

Creates the dynamic loss scale.

#### Args:

* <b>`initial_loss_scale`</b>: A Python float.  The loss scale to use at the
    beginning. It's better to start this at a very high number, because a
    loss scale that is too high gets lowered far more quickly than a loss
    scale that is too low gets raised. The default is 2 ** 15, which is
    approximately half the maximum float16 value.
* <b>`increment_period`</b>: Increases loss scale every `increment_period`
    consecutive steps that finite gradients are encountered. If a nonfinite
    gradient is encountered, the count is reset back to zero.
* <b>`multiplier`</b>: The multiplier to use when increasing or decreasing the loss
    scale.



## Properties

<h3 id="increment_period"><code>increment_period</code></h3>



<h3 id="initial_loss_scale"><code>initial_loss_scale</code></h3>



<h3 id="multiplier"><code>multiplier</code></h3>





## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__()
```

Returns the current loss scale as a scalar `float32` tensor.

<h3 id="from_config"><code>from_config</code></h3>

``` python
from_config(
    cls,
    config
)
```

Creates the LossScale from its config.

<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```

Returns the config of this loss scale.

<h3 id="update"><code>update</code></h3>

``` python
update(grads)
```

Updates loss scale based on if gradients are finite in current step.




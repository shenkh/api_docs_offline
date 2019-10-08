<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.Loss" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="call"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.losses.Loss

## Class `Loss`



### Aliases:

* Class `tf.keras.losses.Loss`
* Class `tf.losses.Loss`



Defined in [`tensorflow/python/keras/losses.py`](/code/stable/tensorflow/python/keras/losses.py).

Loss base class.

To be implemented by subclasses:
* `call()`: Contains the logic for loss calculation using `y_true`, `y_pred`.

Example subclass implementation:
```
class MeanSquaredError(Loss):
  def call(self, y_true, y_pred):
    y_pred = ops.convert_to_tensor(y_pred)
    y_true = math_ops.cast(y_true, y_pred.dtype)
    return K.mean(math_ops.square(y_pred - y_true), axis=-1)
```

When used with <a href="../../tf/distribute/Strategy.md"><code>tf.distribute.Strategy</code></a>, outside of built-in training loops
such as <a href="../../tf/keras.md"><code>tf.keras</code></a> `compile` and `fit`, please use 'SUM' or 'NONE' reduction
types, and reduce losses explicitly in your training loop. Using 'AUTO' or
'SUM_OVER_BATCH_SIZE' will raise an error.

Please see
https://www.tensorflow.org/alpha/tutorials/distribute/training_loops for more
details on this.

You can implement 'SUM_OVER_BATCH_SIZE' using global batch size like:
```
with strategy.scope():
  loss_obj = tf.keras.losses.CategoricalCrossentropy(
      reduction=tf.keras.losses.Reduction.NONE)
  ....
  loss = (tf.reduce_sum(loss_obj(labels, predictions)) *
          (1. / global_batch_size))
```

#### Args:

* <b>`reduction`</b>: (Optional) Type of <a href="../../tf/losses/Reduction.md"><code>tf.keras.losses.Reduction</code></a> to apply to loss.
    Default value is `AUTO`. `AUTO` indicates that the reduction option will
    be determined by the usage context. For almost all cases this defaults to
    `SUM_OVER_BATCH_SIZE`.
    When used with <a href="../../tf/distribute/Strategy.md"><code>tf.distribute.Strategy</code></a>, outside of built-in training
    loops such as <a href="../../tf/keras.md"><code>tf.keras</code></a> `compile` and `fit`, using `AUTO` or
    `SUM_OVER_BATCH_SIZE` will raise an error. Please see
    https://www.tensorflow.org/alpha/tutorials/distribute/training_loops
    for more details on this.
* <b>`name`</b>: Optional name for the op.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    reduction=losses_utils.ReductionV2.AUTO,
    name=None
)
```

Initialize self.  See help(type(self)) for accurate signature.



## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    y_true,
    y_pred,
    sample_weight=None
)
```

Invokes the `Loss` instance.

#### Args:

* <b>`y_true`</b>: Ground truth values. shape = `[batch_size, d0, .. dN]`
* <b>`y_pred`</b>: The predicted values. shape = `[batch_size, d0, .. dN]`
* <b>`sample_weight`</b>: Optional `sample_weight` acts as a
    coefficient for the loss. If a scalar is provided, then the loss is
    simply scaled by the given value. If `sample_weight` is a tensor of size
    `[batch_size]`, then the total loss for each sample of the batch is
    rescaled by the corresponding element in the `sample_weight` vector. If
    the shape of `sample_weight` is `[batch_size, d0, .. dN-1]` (or can be
    broadcasted to this shape), then each loss element of `y_pred` is scaled
    by the corresponding value of `sample_weight`. (Note on`dN-1`: all loss
    functions reduce by 1 dimension, usually axis=-1.)


#### Returns:

Weighted loss float `Tensor`. If `reduction` is `NONE`, this has
  shape `[batch_size, d0, .. dN-1]`; otherwise, it is scalar. (Note `dN-1`
  because all loss functions reduce by 1 dimension, usually axis=-1.)


#### Raises:

* <b>`ValueError`</b>: If the shape of `sample_weight` is invalid.

<h3 id="call"><code>call</code></h3>

``` python
call(
    y_true,
    y_pred
)
```

Invokes the `Loss` instance.

#### Args:

* <b>`y_true`</b>: Ground truth values, with the same shape as 'y_pred'.
* <b>`y_pred`</b>: The predicted values.

<h3 id="from_config"><code>from_config</code></h3>

``` python
@classmethod
from_config(
    cls,
    config
)
```

Instantiates a `Loss` from its config (output of `get_config()`).

#### Args:

* <b>`config`</b>: Output of `get_config()`.


#### Returns:

A `Loss` instance.

<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```






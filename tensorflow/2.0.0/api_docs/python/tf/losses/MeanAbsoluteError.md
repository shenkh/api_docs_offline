<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.MeanAbsoluteError" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.losses.MeanAbsoluteError

## Class `MeanAbsoluteError`



### Aliases:

* Class `tf.keras.losses.MeanAbsoluteError`
* Class `tf.losses.MeanAbsoluteError`



Defined in [`tensorflow/python/keras/losses.py`](/code/stable/tensorflow/python/keras/losses.py).

Computes the mean of absolute difference between labels and predictions.

`loss = abs(y_true - y_pred)`

Usage:

```python
mae = tf.keras.losses.MeanAbsoluteError()
loss = mae([0., 0., 1., 1.], [1., 1., 1., 0.])
print('Loss: ', loss.numpy())  # Loss: 0.75
```

Usage with the `compile` API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile('sgd', loss=tf.keras.losses.MeanAbsoluteError())
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    reduction=losses_utils.ReductionV2.AUTO,
    name='mean_absolute_error'
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

<h3 id="from_config"><code>from_config</code></h3>

``` python
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






<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.SparseCategoricalCrossentropy" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.losses.SparseCategoricalCrossentropy

## Class `SparseCategoricalCrossentropy`



### Aliases:

* Class `tf.keras.losses.SparseCategoricalCrossentropy`
* Class `tf.losses.SparseCategoricalCrossentropy`



Defined in [`tensorflow/python/keras/losses.py`](/code/stable/tensorflow/python/keras/losses.py).

Computes the crossentropy loss between the labels and predictions.

Use this crossentropy loss function when there are two or more label classes.
We expect labels to be provided as integers. If you want to provide labels
using `one-hot` representation, please use `CategoricalCrossentropy` loss.
There should be `# classes` floating point values per feature for `y_pred`
and a single floating point value per feature for `y_true`.

In the snippet below, there is a single floating point value per example for
`y_true` and `# classes` floating pointing values per example for `y_pred`.
The shape of `y_true` is `[batch_size]` and the shape of `y_pred` is
`[batch_size, num_classes]`.

Usage:

```python
cce = tf.keras.losses.SparseCategoricalCrossentropy()
loss = cce(
  [0, 1, 2],
  [[.9, .05, .05], [.5, .89, .6], [.05, .01, .94]])
print('Loss: ', loss.numpy())  # Loss: 0.3239
```

Usage with the `compile` API:

```python
model = tf.keras.Model(inputs, outputs)
model.compile('sgd', loss=tf.keras.losses.SparseCategoricalCrossentropy())
```

#### Args:

* <b>`from_logits`</b>: Whether `y_pred` is expected to be a logits tensor. By default,
    we assume that `y_pred` encodes a probability distribution.
* <b>`Note`</b>: Using from_logits=True may be more numerically stable.
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
    from_logits=False,
    reduction=losses_utils.ReductionV2.AUTO,
    name='sparse_categorical_crossentropy'
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






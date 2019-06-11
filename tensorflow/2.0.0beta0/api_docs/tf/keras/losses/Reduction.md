<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.Reduction" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="all"/>
<meta itemprop="property" content="validate"/>
<meta itemprop="property" content="AUTO"/>
<meta itemprop="property" content="NONE"/>
<meta itemprop="property" content="SUM"/>
<meta itemprop="property" content="SUM_OVER_BATCH_SIZE"/>
</div>

# tf.keras.losses.Reduction

## Class `Reduction`

Types of loss reduction.



### Aliases:

* Class `tf.compat.v2.keras.losses.Reduction`
* Class `tf.compat.v2.losses.Reduction`
* Class `tf.keras.losses.Reduction`
* Class `tf.losses.Reduction`



Defined in [`python/ops/losses/loss_reduction.py`](/code/stable/tensorflow/python/ops/losses/loss_reduction.py).

<!-- Placeholder for "Used in" -->

Contains the following values:

* `AUTO`: Indicates that the reduction option will be determined by the usage
   context. For almost all cases this defaults to `SUM_OVER_BATCH_SIZE`. When
   used with <a href="../../../tf/distribute/Strategy.md"><code>tf.distribute.Strategy</code></a>, outside of built-in training loops such
   as <a href="../../../tf/keras.md"><code>tf.keras</code></a> `compile` and `fit`, we expect reduction value to be
   `SUM` or `NONE`. Using `AUTO` in that case will raise an error.
* `NONE`: Un-reduced weighted losses with the same shape as input. When this
  reduction type used with built-in Keras training loops like
  `fit`/`evaluate`, the unreduced vector loss is passed to the optimizer but
  the reported loss will be a scalar value.
* `SUM`: Scalar sum of weighted losses.
* `SUM_OVER_BATCH_SIZE`: Scalar `SUM` divided by number of elements in losses.
   This reduction type is not supported when used with
   <a href="../../../tf/distribute/Strategy.md"><code>tf.distribute.Strategy</code></a> outside of built-in training loops like <a href="../../../tf/keras.md"><code>tf.keras</code></a>
   `compile`/`fit`.

   You can implement 'SUM_OVER_BATCH_SIZE' using global batch size like:
   ```
   with strategy.scope():
     loss_obj = tf.keras.losses.CategoricalCrossentropy(
         reduction=tf.keras.losses.Reduction.None)
     ....
     loss = tf.reduce_sum(loss_object(labels, predictions)) *
         (1. / global_batch_size)
   ```

   Please see
   https://www.tensorflow.org/alpha/tutorials/distribute/training_loops for
   more details on this.

## Methods

<h3 id="all"><code>all</code></h3>

``` python
@classmethod
all(cls)
```




<h3 id="validate"><code>validate</code></h3>

``` python
@classmethod
validate(
    cls,
    key
)
```






## Class Members

* `AUTO = 'auto'` <a id="AUTO"></a>
* `NONE = 'none'` <a id="NONE"></a>
* `SUM = 'sum'` <a id="SUM"></a>
* `SUM_OVER_BATCH_SIZE = 'sum_over_batch_size'` <a id="SUM_OVER_BATCH_SIZE"></a>

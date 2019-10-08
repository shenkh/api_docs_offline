<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.optimizers.schedules.LearningRateSchedule" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.optimizers.schedules.LearningRateSchedule

## Class `LearningRateSchedule`



### Aliases:

* Class `tf.keras.optimizers.schedules.LearningRateSchedule`
* Class `tf.optimizers.schedules.LearningRateSchedule`



Defined in [`tensorflow/python/keras/optimizer_v2/learning_rate_schedule.py`](/code/stable/tensorflow/python/keras/optimizer_v2/learning_rate_schedule.py).

A serializable learning rate decay schedule.

`LearningRateSchedule`s can be passed in as the learning rate of optimizers in
<a href="../../../tf/optimizers.md"><code>tf.keras.optimizers</code></a>. They can be serialized and deserialized using
<a href="../../../tf/optimizers/schedules/serialize.md"><code>tf.keras.optimizers.schedules.serialize</code></a> and
<a href="../../../tf/optimizers/schedules/deserialize.md"><code>tf.keras.optimizers.schedules.deserialize</code></a>.

## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(step)
```

Call self as a function.

<h3 id="from_config"><code>from_config</code></h3>

``` python
@classmethod
from_config(
    cls,
    config
)
```

Instantiates a `LearningRateSchedule` from its config.

#### Args:

* <b>`config`</b>: Output of `get_config()`.


#### Returns:

A `LearningRateSchedule` instance.

<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```






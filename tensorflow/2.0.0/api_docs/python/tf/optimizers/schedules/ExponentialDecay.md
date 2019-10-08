<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.optimizers.schedules.ExponentialDecay" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.optimizers.schedules.ExponentialDecay

## Class `ExponentialDecay`

Inherits From: [`LearningRateSchedule`](../../../tf/optimizers/schedules/LearningRateSchedule.md)

### Aliases:

* Class `tf.keras.optimizers.schedules.ExponentialDecay`
* Class `tf.optimizers.schedules.ExponentialDecay`



Defined in [`tensorflow/python/keras/optimizer_v2/learning_rate_schedule.py`](/code/stable/tensorflow/python/keras/optimizer_v2/learning_rate_schedule.py).

A LearningRateSchedule that uses an exponential decay schedule.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    initial_learning_rate,
    decay_steps,
    decay_rate,
    staircase=False,
    name=None
)
```

Applies exponential decay to the learning rate.

When training a model, it is often recommended to lower the learning rate as
the training progresses. This schedule applies an exponential decay function
to an optimizer step, given a provided initial learning rate.

The schedule a 1-arg callable that produces a decayed learning
rate when passed the current optimizer step. This can be useful for changing
the learning rate value across different invocations of optimizer functions.
It is computed as:

```python
def decayed_learning_rate(step):
  return initial_learning_rate * decay_rate ^ (step / decay_steps)
```

If the argument `staircase` is `True`, then `step / decay_steps` is
an integer division and the decayed learning rate follows a
staircase function.

You can pass this schedule directly into a <a href="../../../tf/optimizers/Optimizer.md"><code>tf.keras.optimizers.Optimizer</code></a>
as the learning rate.
Example: When fitting a Keras model, decay every 100000 steps with a base
of 0.96:

```python
initial_learning_rate = 0.1
lr_schedule = tf.keras.optimizers.schedules.ExponentialDecay(
    initial_learning_rate,
    decay_steps=100000,
    decay_rate=0.96,
    staircase=True)

model.compile(optimizer=tf.keras.optimizers.SGD(learning_rate=lr_schedule),
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])

model.fit(data, labels, epochs=5)
```

The learning rate schedule is also serializable and deserializable using
<a href="../../../tf/optimizers/schedules/serialize.md"><code>tf.keras.optimizers.schedules.serialize</code></a> and
<a href="../../../tf/optimizers/schedules/deserialize.md"><code>tf.keras.optimizers.schedules.deserialize</code></a>.

#### Args:

* <b>`initial_learning_rate`</b>: A scalar `float32` or `float64` `Tensor` or a
    Python number.  The initial learning rate.
* <b>`decay_steps`</b>: A scalar `int32` or `int64` `Tensor` or a Python number.
    Must be positive.  See the decay computation above.
* <b>`decay_rate`</b>: A scalar `float32` or `float64` `Tensor` or a
    Python number.  The decay rate.
* <b>`staircase`</b>: Boolean.  If `True` decay the learning rate at discrete
    intervals
* <b>`name`</b>: String.  Optional name of the operation.  Defaults to
    'ExponentialDecay'.


#### Returns:

A 1-arg callable learning rate schedule that takes the current optimizer
step and outputs the decayed learning rate, a scalar `Tensor` of the same
type as `initial_learning_rate`.



## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(step)
```

Call self as a function.

<h3 id="from_config"><code>from_config</code></h3>

``` python
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






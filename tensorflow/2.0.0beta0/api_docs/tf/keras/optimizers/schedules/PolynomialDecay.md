<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.optimizers.schedules.PolynomialDecay" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.keras.optimizers.schedules.PolynomialDecay

## Class `PolynomialDecay`

A LearningRateSchedule that uses a polynomial decay schedule.

Inherits From: [`LearningRateSchedule`](../../../../tf/keras/optimizers/schedules/LearningRateSchedule.md)

### Aliases:

* Class `tf.compat.v1.keras.optimizers.schedules.PolynomialDecay`
* Class `tf.compat.v2.keras.optimizers.schedules.PolynomialDecay`
* Class `tf.compat.v2.optimizers.schedules.PolynomialDecay`
* Class `tf.keras.optimizers.schedules.PolynomialDecay`
* Class `tf.optimizers.schedules.PolynomialDecay`



Defined in [`python/keras/optimizer_v2/learning_rate_schedule.py`](/code/stable/tensorflow/python/keras/optimizer_v2/learning_rate_schedule.py).

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    initial_learning_rate,
    decay_steps,
    end_learning_rate=0.0001,
    power=1.0,
    cycle=False,
    name=None
)
```

Applies a polynomial decay to the learning rate.

It is commonly observed that a monotonically decreasing learning rate, whose
degree of change is carefully chosen, results in a better performing model.
This schedule applies a polynomial decay function to an optimizer step,
given a provided `initial_learning_rate`, to reach an `end_learning_rate`
in the given `decay_steps`.

It requires a `step` value to compute the decayed learning rate. You
can just pass a TensorFlow variable that you increment at each training
step.

The schedule is a 1-arg callable that produces a decayed learning rate
when passed the current optimizer step. This can be useful for changing the
learning rate value across different invocations of optimizer functions.
It is computed as:

```python
def decayed_learning_rate(step):
  step = min(step, decay_steps)
  return ((initial_learning_rate - end_learning_rate) *
          (1 - step / decay_steps) ^ (power)
         ) + end_learning_rate
```

If `cycle` is True then a multiple of `decay_steps` is used, the first one
that is bigger than `step`.

```python
def decayed_learning_rate(step):
  decay_steps = decay_steps * ceil(step / decay_steps)
  return ((initial_learning_rate - end_learning_rate) *
          (1 - step / decay_steps) ^ (power)
         ) + end_learning_rate
```

You can pass this schedule directly into a <a href="../../../../tf/keras/optimizers/Optimizer.md"><code>tf.keras.optimizers.Optimizer</code></a>
as the learning rate.
Example: Fit a model while decaying from 0.1 to 0.01 in 10000 steps using
sqrt (i.e. power=0.5):

```python
...
starter_learning_rate = 0.1
end_learning_rate = 0.01
decay_steps = 10000
learning_rate_fn = tf.keras.optimizers.schedules.PolynomialDecay(
    starter_learning_rate,
    decay_steps,
    end_learning_rate,
    power=0.5)

model.compile(optimizer=tf.keras.optimizers.SGD(
                  learning_rate=learning_rate_fn),
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])

model.fit(data, labels, epochs=5)
```

The learning rate schedule is also serializable and deserializable using
<a href="../../../../tf/keras/optimizers/schedules/serialize.md"><code>tf.keras.optimizers.schedules.serialize</code></a> and
<a href="../../../../tf/keras/optimizers/schedules/deserialize.md"><code>tf.keras.optimizers.schedules.deserialize</code></a>.

#### Args:


* <b>`initial_learning_rate`</b>: A scalar `float32` or `float64` `Tensor` or a
  Python number.  The initial learning rate.
* <b>`decay_steps`</b>: A scalar `int32` or `int64` `Tensor` or a Python number.
  Must be positive.  See the decay computation above.
* <b>`end_learning_rate`</b>: A scalar `float32` or `float64` `Tensor` or a
  Python number.  The minimal end learning rate.
* <b>`power`</b>: A scalar `float32` or `float64` `Tensor` or a
  Python number.  The power of the polynomial. Defaults to linear, 1.0.
* <b>`cycle`</b>: A boolean, whether or not it should cycle beyond decay_steps.
* <b>`name`</b>: String.  Optional name of the operation. Defaults to
  'PolynomialDecay'.


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







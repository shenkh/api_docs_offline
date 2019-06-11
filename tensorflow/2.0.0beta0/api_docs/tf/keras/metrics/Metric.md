<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.Metric" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="add_weight"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="update_state"/>
</div>

# tf.keras.metrics.Metric

## Class `Metric`

Encapsulates metric logic and state.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

### Aliases:

* Class `tf.compat.v1.keras.metrics.Metric`
* Class `tf.compat.v2.keras.metrics.Metric`
* Class `tf.compat.v2.metrics.Metric`
* Class `tf.keras.metrics.Metric`
* Class `tf.metrics.Metric`



Defined in [`python/keras/metrics.py`](/code/stable/tensorflow/python/keras/metrics.py).

<!-- Placeholder for "Used in" -->


#### Usage:



```python
m = SomeMetric(...)
for input in ...:
  m.update_state(input)
print('Final result: ', m.result().numpy())
```

Usage with tf.keras API:

```python
model = tf.keras.Sequential()
model.add(tf.keras.layers.Dense(64, activation='relu'))
model.add(tf.keras.layers.Dense(64, activation='relu'))
model.add(tf.keras.layers.Dense(10, activation='softmax'))

model.compile(optimizer=tf.compat.v1.train.RMSPropOptimizer(0.01),
              loss=tf.keras.losses.categorical_crossentropy,
              metrics=[tf.keras.metrics.CategoricalAccuracy()])

data = np.random.random((1000, 32))
labels = np.random.random((1000, 10))

dataset = tf.data.Dataset.from_tensor_slices((data, labels))
dataset = dataset.batch(32)
dataset = dataset.repeat()

model.fit(dataset, epochs=10, steps_per_epoch=30)
```

To be implemented by subclasses:
* `__init__()`: All state variables should be created in this method by
  calling `self.add_weight()` like: `self.var = self.add_weight(...)`
* `update_state()`: Has all updates to the state variables like:
  self.var.assign_add(...).
* `result()`: Computes and returns a value for the metric
  from the state variables.

Example subclass implementation:

```
class BinaryTruePositives(tf.keras.metrics.Metric):

  def __init__(self, name='binary_true_positives', **kwargs):
    super(BinaryTruePositives, self).__init__(name=name, **kwargs)
    self.true_positives = self.add_weight(name='tp', initializer='zeros')

  def update_state(self, y_true, y_pred, sample_weight=None):
    y_true = tf.cast(y_true, tf.bool)
    y_pred = tf.cast(y_pred, tf.bool)

    values = tf.logical_and(tf.equal(y_true, True), tf.equal(y_pred, True))
    values = tf.cast(values, self.dtype)
    if sample_weight is not None:
      sample_weight = tf.cast(sample_weight, self.dtype)
      sample_weight = tf.broadcast_weights(sample_weight, values)
      values = tf.multiply(values, sample_weight)
    self.true_positives.assign_add(tf.reduce_sum(values))

  def result(self):
    return self.true_positives
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    name=None,
    dtype=None,
    **kwargs
)
```






## Methods

<h3 id="add_weight"><code>add_weight</code></h3>

``` python
add_weight(
    name,
    shape=(),
    aggregation=tf.compat.v1.VariableAggregation.SUM,
    synchronization=tf.VariableSynchronization.ON_READ,
    initializer=None,
    dtype=None
)
```

Adds state variable. Only for use by subclasses.


<h3 id="reset_states"><code>reset_states</code></h3>

``` python
reset_states()
```

Resets all of the metric state variables.

This function is called between epochs/steps,
when a metric is evaluated during training.

<h3 id="result"><code>result</code></h3>

``` python
result()
```

Computes and returns the metric value tensor.

Result computation is an idempotent operation that simply calculates the
metric value using the state variables.

<h3 id="update_state"><code>update_state</code></h3>

``` python
update_state(
    *args,
    **kwargs
)
```

Accumulates statistics for the metric.

Note: This function is executed as a graph function in graph mode.
This means:
  a) Operations on the same resource are executed in textual order.
     This should make it easier to do things like add the updated
     value of a variable to another, for example.
  b) You don't need to worry about collecting the update ops to execute.
     All update ops added to the graph by this function will be executed.
  As a result, code should generally work the same way with graph or
  eager execution.

Please use `tf.config.experimental_run_functions_eagerly(True)` to execute
this function eagerly for debugging or profiling.

#### Args:


* <b>`*args`</b>: * <b>`**kwargs`</b>: A mini-batch of inputs to the Metric.




<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.Sequential" />
<meta itemprop="property" content="activity_regularizer"/>
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="inbound_nodes"/>
<meta itemprop="property" content="input"/>
<meta itemprop="property" content="input_mask"/>
<meta itemprop="property" content="input_shape"/>
<meta itemprop="property" content="input_spec"/>
<meta itemprop="property" content="layers"/>
<meta itemprop="property" content="losses"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="non_trainable_variables"/>
<meta itemprop="property" content="non_trainable_weights"/>
<meta itemprop="property" content="outbound_nodes"/>
<meta itemprop="property" content="output"/>
<meta itemprop="property" content="output_mask"/>
<meta itemprop="property" content="output_shape"/>
<meta itemprop="property" content="state_updates"/>
<meta itemprop="property" content="stateful"/>
<meta itemprop="property" content="trainable_variables"/>
<meta itemprop="property" content="trainable_weights"/>
<meta itemprop="property" content="updates"/>
<meta itemprop="property" content="uses_learning_phase"/>
<meta itemprop="property" content="variables"/>
<meta itemprop="property" content="weights"/>
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__setattr__"/>
<meta itemprop="property" content="add"/>
<meta itemprop="property" content="add_loss"/>
<meta itemprop="property" content="add_update"/>
<meta itemprop="property" content="add_variable"/>
<meta itemprop="property" content="add_weight"/>
<meta itemprop="property" content="apply"/>
<meta itemprop="property" content="build"/>
<meta itemprop="property" content="call"/>
<meta itemprop="property" content="compile"/>
<meta itemprop="property" content="compute_mask"/>
<meta itemprop="property" content="compute_output_shape"/>
<meta itemprop="property" content="count_params"/>
<meta itemprop="property" content="evaluate"/>
<meta itemprop="property" content="evaluate_generator"/>
<meta itemprop="property" content="fit"/>
<meta itemprop="property" content="fit_generator"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
<meta itemprop="property" content="get_input_at"/>
<meta itemprop="property" content="get_input_mask_at"/>
<meta itemprop="property" content="get_input_shape_at"/>
<meta itemprop="property" content="get_layer"/>
<meta itemprop="property" content="get_losses_for"/>
<meta itemprop="property" content="get_output_at"/>
<meta itemprop="property" content="get_output_mask_at"/>
<meta itemprop="property" content="get_output_shape_at"/>
<meta itemprop="property" content="get_updates_for"/>
<meta itemprop="property" content="get_weights"/>
<meta itemprop="property" content="load_weights"/>
<meta itemprop="property" content="pop"/>
<meta itemprop="property" content="predict"/>
<meta itemprop="property" content="predict_classes"/>
<meta itemprop="property" content="predict_generator"/>
<meta itemprop="property" content="predict_on_batch"/>
<meta itemprop="property" content="predict_proba"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="save"/>
<meta itemprop="property" content="save_weights"/>
<meta itemprop="property" content="set_weights"/>
<meta itemprop="property" content="summary"/>
<meta itemprop="property" content="test_on_batch"/>
<meta itemprop="property" content="to_json"/>
<meta itemprop="property" content="to_yaml"/>
<meta itemprop="property" content="train_on_batch"/>
</div>

# tf.keras.Sequential

## Class `Sequential`

Inherits From: [`Model`](../../tf/keras/Model.md)

### Aliases:

* Class `tf.keras.Sequential`
* Class `tf.keras.models.Sequential`



Defined in [`tensorflow/python/keras/engine/sequential.py`](https://www.tensorflow.org/code/tensorflow/python/keras/engine/sequential.py).

Linear stack of layers.

#### Arguments:

* <b>`layers`</b>: list of layers to add to the model.

Example:

```python
# Optionally, the first layer can receive an `input_shape` argument:
model = Sequential()
model.add(Dense(32, input_shape=(500,)))
# Afterwards, we do automatic shape inference:
model.add(Dense(32))

# This is identical to the following:
model = Sequential()
model.add(Dense(32, input_dim=500))

# And to the following:
model = Sequential()
model.add(Dense(32, batch_input_shape=(None, 500)))

# Note that you can also omit the `input_shape` argument:
# In that case the model gets built the first time you call `fit` (or other
# training and evaluation methods).
model = Sequential()
model.add(Dense(32))
model.add(Dense(32))
model.compile(optimizer=optimizer, loss=loss)
# This builds the model for the first time:
model.fit(x, y, batch_size=32, epochs=10)

# Note that when using this delayed-build pattern (no input shape specified),
# the model doesn't have any weights until the first call
# to a training/evaluation method (since it isn't yet built):
model = Sequential()
model.add(Dense(32))
model.add(Dense(32))
model.weights  # returns []

# Whereas if you specify the input shape, the model gets built continuously
# as you are adding layers:
model = Sequential()
model.add(Dense(32, input_shape=(500,)))
model.add(Dense(32))
model.weights  # returns list of length 4

When using the delayed-build pattern (no input shape specified), you can
choose to manually build your model by calling `build(batch_input_shape)`:
model = Sequential()
model.add(Dense(32))
model.add(Dense(32))
model.build((None, 500))
model.weights  # returns list of length 4
```

## Properties

<h3 id="activity_regularizer"><code>activity_regularizer</code></h3>

Optional regularizer function for the output of this layer.

<h3 id="dtype"><code>dtype</code></h3>



<h3 id="inbound_nodes"><code>inbound_nodes</code></h3>

Deprecated, do NOT use! Only for compatibility with external Keras.

<h3 id="input"><code>input</code></h3>

Retrieves the input tensor(s) of a layer.

Only applicable if the layer has exactly one input,
i.e. if it is connected to one incoming layer.

#### Returns:

Input tensor or list of input tensors.


#### Raises:

* <b>`AttributeError`</b>: if the layer is connected to
    more than one incoming layers.


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.
* <b>`AttributeError`</b>: If no inbound nodes are found.

<h3 id="input_mask"><code>input_mask</code></h3>

Retrieves the input mask tensor(s) of a layer.

Only applicable if the layer has exactly one inbound node,
i.e. if it is connected to one incoming layer.

#### Returns:

Input mask tensor (potentially None) or list of input
mask tensors.


#### Raises:

* <b>`AttributeError`</b>: if the layer is connected to
    more than one incoming layers.

<h3 id="input_shape"><code>input_shape</code></h3>

Retrieves the input shape(s) of a layer.

Only applicable if the layer has exactly one input,
i.e. if it is connected to one incoming layer, or if all inputs
have the same shape.

#### Returns:

Input shape, as an integer shape tuple
(or list of shape tuples, one tuple per input tensor).


#### Raises:

* <b>`AttributeError`</b>: if the layer has no defined input_shape.
* <b>`RuntimeError`</b>: if called in Eager mode.

<h3 id="input_spec"><code>input_spec</code></h3>

Gets the network's input specs.

#### Returns:

A list of `InputSpec` instances (one per input to the model)
    or a single instance if the model has only one input.

<h3 id="layers"><code>layers</code></h3>



<h3 id="losses"><code>losses</code></h3>

Retrieves the network's losses.

Will only include losses that are either
unconditional, or conditional on inputs to this model
(e.g. will not include losses that depend on tensors
that aren't inputs to this model).

When the network has no registered inputs, all losses are returned.

#### Returns:

A list of loss tensors.

<h3 id="name"><code>name</code></h3>



<h3 id="non_trainable_variables"><code>non_trainable_variables</code></h3>



<h3 id="non_trainable_weights"><code>non_trainable_weights</code></h3>



<h3 id="outbound_nodes"><code>outbound_nodes</code></h3>

Deprecated, do NOT use! Only for compatibility with external Keras.

<h3 id="output"><code>output</code></h3>

Retrieves the output tensor(s) of a layer.

Only applicable if the layer has exactly one output,
i.e. if it is connected to one incoming layer.

#### Returns:

Output tensor or list of output tensors.


#### Raises:

* <b>`AttributeError`</b>: if the layer is connected to more than one incoming
    layers.
* <b>`RuntimeError`</b>: if called in Eager mode.

<h3 id="output_mask"><code>output_mask</code></h3>

Retrieves the output mask tensor(s) of a layer.

Only applicable if the layer has exactly one inbound node,
i.e. if it is connected to one incoming layer.

#### Returns:

Output mask tensor (potentially None) or list of output
mask tensors.


#### Raises:

* <b>`AttributeError`</b>: if the layer is connected to
    more than one incoming layers.

<h3 id="output_shape"><code>output_shape</code></h3>

Retrieves the output shape(s) of a layer.

Only applicable if the layer has one output,
or if all outputs have the same shape.

#### Returns:

Output shape, as an integer shape tuple
(or list of shape tuples, one tuple per output tensor).


#### Raises:

* <b>`AttributeError`</b>: if the layer has no defined output shape.
* <b>`RuntimeError`</b>: if called in Eager mode.

<h3 id="state_updates"><code>state_updates</code></h3>

Returns the `updates` from all layers that are stateful.

This is useful for separating training updates and
state updates, e.g. when we need to update a layer's internal state
during prediction.

#### Returns:

A list of update ops.

<h3 id="stateful"><code>stateful</code></h3>



<h3 id="trainable_variables"><code>trainable_variables</code></h3>



<h3 id="trainable_weights"><code>trainable_weights</code></h3>



<h3 id="updates"><code>updates</code></h3>

Retrieves the network's updates.

Will only include updates that are either
unconditional, or conditional on inputs to this model
(e.g. will not include updates that were created by layers of this model
outside of the model).

When the network has no registered inputs, all updates are returned.

Effectively, `network.updates` behaves like `layer.updates`.

Concrete example:

```python
  bn = keras.layers.BatchNormalization()
  x1 = keras.layers.Input(shape=(10,))
  _ = bn(x1)  # This creates 2 updates.

  x2 = keras.layers.Input(shape=(10,))
  y2 = bn(x2)  # This creates 2 more updates.

  # The BN layer has now 4 updates.
  self.assertEqual(len(bn.updates), 4)

  # Let's create a model from x2 to y2.
  model = keras.models.Model(x2, y2)

  # The model does not list all updates from its underlying layers,
  # but only the updates that are relevant to it. Updates created by layers
  # outside of the model are discarded.
  self.assertEqual(len(model.updates), 2)

  # If you keep calling the model, you append to its updates, just like
  # what happens for a layer.
  x3 = keras.layers.Input(shape=(10,))
  y3 = model(x3)
  self.assertEqual(len(model.updates), 4)

  # But if you call the inner BN layer independently, you don't affect
  # the model's updates.
  x4 = keras.layers.Input(shape=(10,))
  _ = bn(x4)
  self.assertEqual(len(model.updates), 4)
```

#### Returns:

A list of update ops.

<h3 id="uses_learning_phase"><code>uses_learning_phase</code></h3>



<h3 id="variables"><code>variables</code></h3>

Returns the list of all layer variables/weights.

#### Returns:

A list of variables.

<h3 id="weights"><code>weights</code></h3>

Returns the list of all layer variables/weights.

#### Returns:

A list of variables.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    layers=None,
    name=None
)
```



<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    inputs,
    *args,
    **kwargs
)
```

Wraps `call`, applying pre- and post-processing steps.

#### Arguments:

* <b>`inputs`</b>: input tensor(s).
* <b>`*args`</b>: additional positional arguments to be passed to `self.call`.
* <b>`**kwargs`</b>: additional keyword arguments to be passed to `self.call`.


#### Returns:

  Output tensor(s).

Note:
  - The following optional keyword arguments are reserved for specific uses:
    * `training`: Boolean scalar tensor of Python boolean indicating
      whether the `call` is meant for training or inference.
    * `mask`: Boolean input mask.
  - If the layer's `call` method takes a `mask` argument (as some Keras
    layers do), its default value will be set to the mask generated
    for `inputs` by the previous layer (if `input` did come from
    a layer that generated a corresponding mask, i.e. if it came from
    a Keras layer with masking support.


#### Raises:

* <b>`ValueError`</b>: if the layer's `call` method returns None (an invalid value).

<h3 id="__setattr__"><code>__setattr__</code></h3>

``` python
__setattr__(
    name,
    value
)
```

Implement setattr(self, name, value).

<h3 id="add"><code>add</code></h3>

``` python
add(layer)
```

Adds a layer instance on top of the layer stack.

#### Arguments:

* <b>`layer`</b>: layer instance.


#### Raises:

* <b>`TypeError`</b>: If `layer` is not a layer instance.
* <b>`ValueError`</b>: In case the `layer` argument does not
        know its input shape.
* <b>`ValueError`</b>: In case the `layer` argument has
        multiple output tensors, or is already connected
        somewhere else (forbidden in `Sequential` models).

<h3 id="add_loss"><code>add_loss</code></h3>

``` python
add_loss(
    *args,
    **kwargs
)
```

Add loss tensor(s), potentially dependent on layer inputs.

Some losses (for instance, activity regularization losses) may be dependent
on the inputs passed when calling a layer. Hence, when reusing the same
layer on different inputs `a` and `b`, some entries in `layer.losses` may
be dependent on `a` and some on `b`. This method automatically keeps track
of dependencies.

The `get_losses_for` method allows to retrieve the losses relevant to a
specific set of inputs.

Note that `add_loss` is not supported when executing eagerly. Instead,
variable regularizers may be added through `add_variable`. Activity
regularization is not supported directly (but such losses may be returned
from `Layer.call()`).

#### Arguments:

* <b>`losses`</b>: Loss tensor, or list/tuple of tensors.
* <b>`inputs`</b>: If anything other than None is passed, it signals the losses
    are conditional on some of the layer's inputs,
    and thus they should only be run where these inputs are available.
    This is the case for activity regularization losses, for instance.
    If `None` is passed, the losses are assumed
    to be unconditional, and will apply across all dataflows of the layer
    (e.g. weight regularization losses).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="add_update"><code>add_update</code></h3>

``` python
add_update(
    updates,
    inputs=None
)
```

Add update op(s), potentially dependent on layer inputs.

Weight updates (for instance, the updates of the moving mean and variance
in a BatchNormalization layer) may be dependent on the inputs passed
when calling a layer. Hence, when reusing the same layer on
different inputs `a` and `b`, some entries in `layer.updates` may be
dependent on `a` and some on `b`. This method automatically keeps track
of dependencies.

The `get_updates_for` method allows to retrieve the updates relevant to a
specific set of inputs.

This call is ignored when eager execution is enabled (in that case, variable
updates are run on the fly and thus do not need to be tracked for later
execution).

#### Arguments:

* <b>`updates`</b>: Update op, or list/tuple of update ops.
* <b>`inputs`</b>: If anything other than None is passed, it signals the updates
    are conditional on some of the layer's inputs,
    and thus they should only be run where these inputs are available.
    This is the case for BatchNormalization updates, for instance.
    If None, the updates will be taken into account unconditionally,
    and you are responsible for making sure that any dependency they might
    have is available at runtime.
    A step counter might fall into this category.

<h3 id="add_variable"><code>add_variable</code></h3>

``` python
add_variable(
    name,
    shape,
    dtype=None,
    initializer=None,
    regularizer=None,
    trainable=True,
    constraint=None
)
```

Alias for `add_weight`.

<h3 id="add_weight"><code>add_weight</code></h3>

``` python
add_weight(
    name,
    shape,
    dtype=None,
    initializer=None,
    regularizer=None,
    trainable=None,
    constraint=None,
    partitioner=None,
    use_resource=None,
    synchronization=tf.VariableSynchronization.AUTO,
    aggregation=tf.VariableAggregation.NONE,
    getter=None
)
```

Adds a new variable to the layer, or gets an existing one; returns it.

#### Arguments:

* <b>`name`</b>: variable name.
* <b>`shape`</b>: variable shape.
* <b>`dtype`</b>: The type of the variable. Defaults to `self.dtype` or `float32`.
* <b>`initializer`</b>: initializer instance (callable).
* <b>`regularizer`</b>: regularizer instance (callable).
* <b>`trainable`</b>: whether the variable should be part of the layer's
    "trainable_variables" (e.g. variables, biases)
    or "non_trainable_variables" (e.g. BatchNorm mean, stddev).
    Note, if the current variable scope is marked as non-trainable
    then this parameter is ignored and any added variables are also
    marked as non-trainable. `trainable` defaults to `True` unless
    `synchronization` is set to `ON_READ`.
* <b>`constraint`</b>: constraint instance (callable).
* <b>`partitioner`</b>: Partitioner to be passed to the `Checkpointable` API.
* <b>`use_resource`</b>: Whether to use `ResourceVariable`.
* <b>`synchronization`</b>: Indicates when a distributed a variable will be
    aggregated. Accepted values are constants defined in the class
    <a href="../../tf/VariableSynchronization.md"><code>tf.VariableSynchronization</code></a>. By default the synchronization is set to
    `AUTO` and the current `DistributionStrategy` chooses
    when to synchronize. If `synchronization` is set to `ON_READ`,
    `trainable` must not be set to `True`.
* <b>`aggregation`</b>: Indicates how a distributed variable will be aggregated.
    Accepted values are constants defined in the class
    <a href="../../tf/VariableAggregation.md"><code>tf.VariableAggregation</code></a>.
* <b>`getter`</b>: Variable getter argument to be passed to the `Checkpointable` API.


#### Returns:

The created variable.  Usually either a `Variable` or `ResourceVariable`
instance.  If `partitioner` is not `None`, a `PartitionedVariable`
instance is returned.


#### Raises:

* <b>`RuntimeError`</b>: If called with partioned variable regularization and
    eager execution is enabled.
* <b>`ValueError`</b>: When giving unsupported dtype and no initializer or when
    trainable has been set to True with synchronization set as `ON_READ`.

<h3 id="apply"><code>apply</code></h3>

``` python
apply(
    inputs,
    *args,
    **kwargs
)
```

Apply the layer on a input.

This simply wraps `self.__call__`.

#### Arguments:

* <b>`inputs`</b>: Input tensor(s).
* <b>`*args`</b>: additional positional arguments to be passed to `self.call`.
* <b>`**kwargs`</b>: additional keyword arguments to be passed to `self.call`.


#### Returns:

Output tensor(s).

<h3 id="build"><code>build</code></h3>

``` python
build(input_shape=None)
```



<h3 id="call"><code>call</code></h3>

``` python
call(
    inputs,
    training=None,
    mask=None
)
```

Calls the model on new inputs.

In this case `call` just reapplies
all ops in the graph to the new inputs
(e.g. build a new computational graph from the provided inputs).

#### Arguments:

* <b>`inputs`</b>: A tensor or list of tensors.
* <b>`training`</b>: Boolean or boolean scalar tensor, indicating whether to run
      the `Network` in training mode or inference mode.
* <b>`mask`</b>: A mask or list of masks. A mask can be
        either a tensor or None (no mask).


#### Returns:

A tensor if there is a single output, or
a list of tensors if there are more than one outputs.

<h3 id="compile"><code>compile</code></h3>

``` python
compile(
    optimizer,
    loss=None,
    metrics=None,
    loss_weights=None,
    sample_weight_mode=None,
    weighted_metrics=None,
    target_tensors=None,
    **kwargs
)
```

Configures the model for training.

#### Arguments:

* <b>`optimizer`</b>: String (name of optimizer) or optimizer instance.
        See [optimizers](/optimizers).
* <b>`loss`</b>: String (name of objective function) or objective function.
        See [losses](/losses).
        If the model has multiple outputs, you can use a different loss
        on each output by passing a dictionary or a list of losses.
        The loss value that will be minimized by the model
        will then be the sum of all individual losses.
* <b>`metrics`</b>: List of metrics to be evaluated by the model
        during training and testing.
        Typically you will use `metrics=['accuracy']`.
        To specify different metrics for different outputs of a
        multi-output model, you could also pass a dictionary,
        such as `metrics={'output_a': 'accuracy'}`.
* <b>`loss_weights`</b>: Optional list or dictionary specifying scalar
        coefficients (Python floats) to weight the loss contributions
        of different model outputs.
        The loss value that will be minimized by the model
        will then be the *weighted sum* of all individual losses,
        weighted by the `loss_weights` coefficients.
        If a list, it is expected to have a 1:1 mapping
        to the model's outputs. If a tensor, it is expected to map
        output names (strings) to scalar coefficients.
* <b>`sample_weight_mode`</b>: If you need to do timestep-wise
        sample weighting (2D weights), set this to `"temporal"`.
        `None` defaults to sample-wise weights (1D).
        If the model has multiple outputs, you can use a different
        `sample_weight_mode` on each output by passing a
        dictionary or a list of modes.
* <b>`weighted_metrics`</b>: List of metrics to be evaluated and weighted
        by sample_weight or class_weight during training and testing.
* <b>`target_tensors`</b>: By default, Keras will create placeholders for the
        model's target, which will be fed with the target data during
        training. If instead you would like to use your own
        target tensors (in turn, Keras will not expect external
        Numpy data for these targets at training time), you
        can specify them via the `target_tensors` argument. It can be
        a single tensor (for a single-output model), a list of tensors,
        or a dict mapping output names to target tensors.
* <b>`**kwargs`</b>: These arguments are passed to <a href="../../tf/InteractiveSession.md#run"><code>tf.Session.run</code></a>.


#### Raises:

* <b>`ValueError`</b>: In case of invalid arguments for
        `optimizer`, `loss`, `metrics` or `sample_weight_mode`.

<h3 id="compute_mask"><code>compute_mask</code></h3>

``` python
compute_mask(
    inputs,
    mask
)
```

Computes an output mask tensor.

#### Arguments:

* <b>`inputs`</b>: Tensor or list of tensors.
* <b>`mask`</b>: Tensor or list of tensors.


#### Returns:

None or a tensor (or list of tensors,
    one per output tensor of the layer).

<h3 id="compute_output_shape"><code>compute_output_shape</code></h3>

``` python
compute_output_shape(input_shape)
```

Computes the output shape of the layer.

Assumes that the layer will be built
to match that input shape provided.

#### Arguments:

* <b>`input_shape`</b>: Shape tuple (tuple of integers)
        or list of shape tuples (one per output tensor of the layer).
        Shape tuples can include None for free dimensions,
        instead of an integer.


#### Returns:

An input shape tuple.

<h3 id="count_params"><code>count_params</code></h3>

``` python
count_params()
```

Count the total number of scalars composing the weights.

#### Returns:

An integer count.


#### Raises:

* <b>`ValueError`</b>: if the layer isn't yet built
      (in which case its weights aren't yet defined).

<h3 id="evaluate"><code>evaluate</code></h3>

``` python
evaluate(
    x=None,
    y=None,
    batch_size=None,
    verbose=1,
    sample_weight=None,
    steps=None
)
```

Returns the loss value & metrics values for the model in test mode.

Computation is done in batches.

#### Arguments:

* <b>`x`</b>: Input data. It could be:
      - A Numpy array (or array-like), or a list of arrays
        (in case the model has multiple inputs).
      - A TensorFlow tensor, or a list of tensors
        (in case the model has multiple inputs).
      - A dict mapping input names to the corresponding array/tensors,
        if the model has named inputs.
      - A <a href="../../tf/data.md"><code>tf.data</code></a> dataset or a dataset iterator.
* <b>`y`</b>: Target data. Like the input data `x`,
      it could be either Numpy array(s) or TensorFlow tensor(s).
      It should be consistent with `x` (you cannot have Numpy inputs and
      tensor targets, or inversely).
      If `x` is a dataset or a dataset iterator, `y` should not be specified
      (since targets will be obtained from the iterator/dataset).
* <b>`batch_size`</b>: Integer or `None`.
        Number of samples per gradient update.
        If unspecified, `batch_size` will default to 32.
        Do not specify the `batch_size` is your data is in the
        form of symbolic tensors, datasets, or dataset iterators
        (since they generate batches).
* <b>`verbose`</b>: 0 or 1. Verbosity mode.
        0 = silent, 1 = progress bar.
* <b>`sample_weight`</b>: Optional Numpy array of weights for
        the test samples, used for weighting the loss function.
        You can either pass a flat (1D)
        Numpy array with the same length as the input samples
        (1:1 mapping between weights and samples),
        or in the case of temporal data,
        you can pass a 2D array with shape
        `(samples, sequence_length)`,
        to apply a different weight to every timestep of every sample.
        In this case you should make sure to specify
        `sample_weight_mode="temporal"` in `compile()`. This argument is not
        supported when `x` is a dataset or a dataset iterator.
* <b>`steps`</b>: Integer or `None`.
        Total number of steps (batches of samples)
        before declaring the evaluation round finished.
        Ignored with the default value of `None`.


#### Returns:

Scalar test loss (if the model has a single output and no metrics)
or list of scalars (if the model has multiple outputs
and/or metrics). The attribute `model.metrics_names` will give you
the display labels for the scalar outputs.


#### Raises:

* <b>`ValueError`</b>: in case of invalid arguments.

<h3 id="evaluate_generator"><code>evaluate_generator</code></h3>

``` python
evaluate_generator(
    generator,
    steps=None,
    max_queue_size=10,
    workers=1,
    use_multiprocessing=False,
    verbose=0
)
```

Evaluates the model on a data generator.

The generator should return the same kind of data
as accepted by `test_on_batch`.

#### Arguments:

* <b>`generator`</b>: Generator yielding tuples (inputs, targets)
        or (inputs, targets, sample_weights)
        or an instance of Sequence (keras.utils.Sequence)
        object in order to avoid duplicate data
        when using multiprocessing.
* <b>`steps`</b>: Total number of steps (batches of samples)
        to yield from `generator` before stopping.
        Optional for `Sequence`: if unspecified, will use
        the `len(generator)` as a number of steps.
* <b>`max_queue_size`</b>: maximum size for the generator queue
* <b>`workers`</b>: Integer. Maximum number of processes to spin up
        when using process-based threading.
        If unspecified, `workers` will default to 1. If 0, will
        execute the generator on the main thread.
* <b>`use_multiprocessing`</b>: Boolean.
        If `True`, use process-based threading.
        If unspecified, `use_multiprocessing` will default to `False`.
        Note that because this implementation relies on multiprocessing,
        you should not pass non-picklable arguments to the generator
        as they can't be passed easily to children processes.
* <b>`verbose`</b>: Verbosity mode, 0 or 1.


#### Returns:

Scalar test loss (if the model has a single output and no metrics)
or list of scalars (if the model has multiple outputs
and/or metrics). The attribute `model.metrics_names` will give you
the display labels for the scalar outputs.


#### Raises:

* <b>`ValueError`</b>: in case of invalid arguments.


#### Raises:

* <b>`ValueError`</b>: In case the generator yields data in an invalid format.

<h3 id="fit"><code>fit</code></h3>

``` python
fit(
    x=None,
    y=None,
    batch_size=None,
    epochs=1,
    verbose=1,
    callbacks=None,
    validation_split=0.0,
    validation_data=None,
    shuffle=True,
    class_weight=None,
    sample_weight=None,
    initial_epoch=0,
    steps_per_epoch=None,
    validation_steps=None,
    **kwargs
)
```

Trains the model for a fixed number of epochs (iterations on a dataset).

#### Arguments:

* <b>`x`</b>: Input data. It could be:
      - A Numpy array (or array-like), or a list of arrays
        (in case the model has multiple inputs).
      - A TensorFlow tensor, or a list of tensors
        (in case the model has multiple inputs).
      - A dict mapping input names to the corresponding array/tensors,
        if the model has named inputs.
      - A <a href="../../tf/data.md"><code>tf.data</code></a> dataset or a dataset iterator.
* <b>`y`</b>: Target data. Like the input data `x`,
      it could be either Numpy array(s) or TensorFlow tensor(s).
      It should be consistent with `x` (you cannot have Numpy inputs and
      tensor targets, or inversely). If `x` is a dataset or dataset
      iterator, `y` should not be specified
      (since targets will be obtained from the iterator).
* <b>`batch_size`</b>: Integer or `None`.
        Number of samples per gradient update.
        If unspecified, `batch_size` will default to 32.
        Do not specify the `batch_size` if your data is in the
        form of symbolic tensors, datasets, or dataset iterators
        (since they generate batches).
* <b>`epochs`</b>: Integer. Number of epochs to train the model.
        An epoch is an iteration over the entire `x` and `y`
        data provided.
        Note that in conjunction with `initial_epoch`,
        `epochs` is to be understood as "final epoch".
        The model is not trained for a number of iterations
        given by `epochs`, but merely until the epoch
        of index `epochs` is reached.
* <b>`verbose`</b>: Integer. 0, 1, or 2. Verbosity mode.
        0 = silent, 1 = progress bar, 2 = one line per epoch.
* <b>`callbacks`</b>: List of `keras.callbacks.Callback` instances.
        List of callbacks to apply during training.
        See [callbacks](/callbacks).
* <b>`validation_split`</b>: Float between 0 and 1.
        Fraction of the training data to be used as validation data.
        The model will set apart this fraction of the training data,
        will not train on it, and will evaluate
        the loss and any model metrics
        on this data at the end of each epoch.
        The validation data is selected from the last samples
        in the `x` and `y` data provided, before shuffling. This argument is
        not supported when `x` is a dataset or a dataset iterator.
* <b>`validation_data`</b>: Data on which to evaluate
        the loss and any model metrics at the end of each epoch.
        The model will not be trained on this data.
        `validation_data` will override `validation_split`.
        `validation_data` could be:
          - tuple `(x_val, y_val)` of Numpy arrays or tensors
          - tuple `(x_val, y_val, val_sample_weights)` of Numpy arrays
          - dataset or a dataset iterator
* <b>`shuffle`</b>: Boolean (whether to shuffle the training data
        before each epoch) or str (for 'batch').
        'batch' is a special option for dealing with the
        limitations of HDF5 data; it shuffles in batch-sized chunks.
        Has no effect when `steps_per_epoch` is not `None`.
* <b>`class_weight`</b>: Optional dictionary mapping class indices (integers)
        to a weight (float) value, used for weighting the loss function
        (during training only).
        This can be useful to tell the model to
        "pay more attention" to samples from
        an under-represented class.
* <b>`sample_weight`</b>: Optional Numpy array of weights for
        the training samples, used for weighting the loss function
        (during training only). You can either pass a flat (1D)
        Numpy array with the same length as the input samples
        (1:1 mapping between weights and samples),
        or in the case of temporal data,
        you can pass a 2D array with shape
        `(samples, sequence_length)`,
        to apply a different weight to every timestep of every sample.
        In this case you should make sure to specify
        `sample_weight_mode="temporal"` in `compile()`. This argument is not
        supported when `x` is a dataset or a dataset iterator.
* <b>`initial_epoch`</b>: Integer.
        Epoch at which to start training
        (useful for resuming a previous training run).
* <b>`steps_per_epoch`</b>: Integer or `None`.
        Total number of steps (batches of samples)
        before declaring one epoch finished and starting the
        next epoch. When training with input tensors such as
        TensorFlow data tensors, the default `None` is equal to
        the number of samples in your dataset divided by
        the batch size, or 1 if that cannot be determined.
* <b>`validation_steps`</b>: Only relevant if `steps_per_epoch`
        is specified. Total number of steps (batches of samples)
        to validate before stopping.
* <b>`**kwargs`</b>: Used for backwards compatibility.


#### Returns:

A `History` object. Its `History.history` attribute is
a record of training loss values and metrics values
at successive epochs, as well as validation loss values
and validation metrics values (if applicable).


#### Raises:

* <b>`RuntimeError`</b>: If the model was never compiled.
* <b>`ValueError`</b>: In case of mismatch between the provided input data
        and what the model expects.

<h3 id="fit_generator"><code>fit_generator</code></h3>

``` python
fit_generator(
    generator,
    steps_per_epoch=None,
    epochs=1,
    verbose=1,
    callbacks=None,
    validation_data=None,
    validation_steps=None,
    class_weight=None,
    max_queue_size=10,
    workers=1,
    use_multiprocessing=False,
    shuffle=True,
    initial_epoch=0
)
```

Fits the model on data yielded batch-by-batch by a Python generator.

The generator is run in parallel to the model, for efficiency.
For instance, this allows you to do real-time data augmentation
on images on CPU in parallel to training your model on GPU.

The use of `keras.utils.Sequence` guarantees the ordering
and guarantees the single use of every input per epoch when
using `use_multiprocessing=True`.

#### Arguments:

* <b>`generator`</b>: A generator or an instance of `Sequence`
      (`keras.utils.Sequence`)
        object in order to avoid duplicate data
        when using multiprocessing.
        The output of the generator must be either
        - a tuple `(inputs, targets)`
        - a tuple `(inputs, targets, sample_weights)`.
        This tuple (a single output of the generator) makes a single batch.
        Therefore, all arrays in this tuple must have the same length (equal
        to the size of this batch). Different batches may have different
          sizes.
        For example, the last batch of the epoch is commonly smaller than
          the
        others, if the size of the dataset is not divisible by the batch
          size.
        The generator is expected to loop over its data
        indefinitely. An epoch finishes when `steps_per_epoch`
        batches have been seen by the model.
* <b>`steps_per_epoch`</b>: Total number of steps (batches of samples)
        to yield from `generator` before declaring one epoch
        finished and starting the next epoch. It should typically
        be equal to the number of samples of your dataset
        divided by the batch size.
        Optional for `Sequence`: if unspecified, will use
        the `len(generator)` as a number of steps.
* <b>`epochs`</b>: Integer, total number of iterations on the data.
* <b>`verbose`</b>: Verbosity mode, 0, 1, or 2.
* <b>`callbacks`</b>: List of callbacks to be called during training.
* <b>`validation_data`</b>: This can be either
        - a generator for the validation data
        - a tuple (inputs, targets)
        - a tuple (inputs, targets, sample_weights).
* <b>`validation_steps`</b>: Only relevant if `validation_data`
        is a generator. Total number of steps (batches of samples)
        to yield from `generator` before stopping.
        Optional for `Sequence`: if unspecified, will use
        the `len(validation_data)` as a number of steps.
* <b>`class_weight`</b>: Dictionary mapping class indices to a weight
        for the class.
* <b>`max_queue_size`</b>: Integer. Maximum size for the generator queue.
        If unspecified, `max_queue_size` will default to 10.
* <b>`workers`</b>: Integer. Maximum number of processes to spin up
        when using process-based threading.
        If unspecified, `workers` will default to 1. If 0, will
        execute the generator on the main thread.
* <b>`use_multiprocessing`</b>: Boolean.
        If `True`, use process-based threading.
        If unspecified, `use_multiprocessing` will default to `False`.
        Note that because this implementation relies on multiprocessing,
        you should not pass non-picklable arguments to the generator
        as they can't be passed easily to children processes.
* <b>`shuffle`</b>: Boolean. Whether to shuffle the order of the batches at
        the beginning of each epoch. Only used with instances
        of `Sequence` (`keras.utils.Sequence`).
        Has no effect when `steps_per_epoch` is not `None`.
* <b>`initial_epoch`</b>: Epoch at which to start training
        (useful for resuming a previous training run)


#### Returns:

    A `History` object.

Example:

```python
    def generate_arrays_from_file(path):
        while 1:
            f = open(path)
            for line in f:
                # create numpy arrays of input data
                # and labels, from each line in the file
                x1, x2, y = process_line(line)
                yield ({'input_1': x1, 'input_2': x2}, {'output': y})
            f.close()

    model.fit_generator(generate_arrays_from_file('/my_file.txt'),
                        steps_per_epoch=10000, epochs=10)
```

#### Raises:

* <b>`ValueError`</b>: In case the generator yields data in an invalid format.

<h3 id="from_config"><code>from_config</code></h3>

``` python
@classmethod
from_config(
    cls,
    config,
    custom_objects=None
)
```

Instantiates a Model from its config (output of `get_config()`).

#### Arguments:

* <b>`config`</b>: Model config dictionary.
* <b>`custom_objects`</b>: Optional dictionary mapping names
        (strings) to custom classes or functions to be
        considered during deserialization.


#### Returns:

A model instance.


#### Raises:

* <b>`ValueError`</b>: In case of improperly formatted config dict.

<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```

Returns the config of the layer.

A layer config is a Python dictionary (serializable)
containing the configuration of a layer.
The same layer can be reinstantiated later
(without its trained weights) from this configuration.

The config of a layer does not include connectivity
information, nor the layer class name. These are handled
by `Network` (one layer of abstraction above).

#### Returns:

Python dictionary.

<h3 id="get_input_at"><code>get_input_at</code></h3>

``` python
get_input_at(node_index)
```

Retrieves the input tensor(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A tensor (or list of tensors if the layer has multiple inputs).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_input_mask_at"><code>get_input_mask_at</code></h3>

``` python
get_input_mask_at(node_index)
```

Retrieves the input mask tensor(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A mask tensor
(or list of tensors if the layer has multiple inputs).

<h3 id="get_input_shape_at"><code>get_input_shape_at</code></h3>

``` python
get_input_shape_at(node_index)
```

Retrieves the input shape(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A shape tuple
(or list of shape tuples if the layer has multiple inputs).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_layer"><code>get_layer</code></h3>

``` python
get_layer(
    name=None,
    index=None
)
```

Retrieves a layer based on either its name (unique) or index.

If `name` and `index` are both provided, `index` will take precedence.
Indices are based on order of horizontal graph traversal (bottom-up).

#### Arguments:

* <b>`name`</b>: String, name of layer.
* <b>`index`</b>: Integer, index of layer.


#### Returns:

A layer instance.


#### Raises:

* <b>`ValueError`</b>: In case of invalid layer name or index.

<h3 id="get_losses_for"><code>get_losses_for</code></h3>

``` python
get_losses_for(inputs)
```

Retrieves losses relevant to a specific set of inputs.

#### Arguments:

* <b>`inputs`</b>: Input tensor or list/tuple of input tensors.


#### Returns:

List of loss tensors of the layer that depend on `inputs`.


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_output_at"><code>get_output_at</code></h3>

``` python
get_output_at(node_index)
```

Retrieves the output tensor(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A tensor (or list of tensors if the layer has multiple outputs).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_output_mask_at"><code>get_output_mask_at</code></h3>

``` python
get_output_mask_at(node_index)
```

Retrieves the output mask tensor(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A mask tensor
(or list of tensors if the layer has multiple outputs).

<h3 id="get_output_shape_at"><code>get_output_shape_at</code></h3>

``` python
get_output_shape_at(node_index)
```

Retrieves the output shape(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A shape tuple
(or list of shape tuples if the layer has multiple outputs).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_updates_for"><code>get_updates_for</code></h3>

``` python
get_updates_for(inputs)
```

Retrieves updates relevant to a specific set of inputs.

#### Arguments:

* <b>`inputs`</b>: Input tensor or list/tuple of input tensors.


#### Returns:

List of update ops of the layer that depend on `inputs`.


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_weights"><code>get_weights</code></h3>

``` python
get_weights()
```

Retrieves the weights of the model.

#### Returns:

A flat list of Numpy arrays.

<h3 id="load_weights"><code>load_weights</code></h3>

``` python
load_weights(
    filepath,
    by_name=False
)
```

Loads all layer weights, either from a TensorFlow or an HDF5 weight file.

If `by_name` is False weights are loaded based on the network's
topology. This means the architecture should be the same as when the weights
were saved.  Note that layers that don't have weights are not taken into
account in the topological ordering, so adding or removing layers is fine as
long as they don't have weights.

If `by_name` is True, weights are loaded into layers only if they share the
same name. This is useful for fine-tuning or transfer-learning models where
some of the layers have changed.

Only topological loading (`by_name=False`) is supported when loading weights
from the TensorFlow format. Note that topological loading differs slightly
between TensorFlow and HDF5 formats for user-defined classes inheriting from
<a href="../../tf/keras/Model.md"><code>tf.keras.Model</code></a>: HDF5 loads based on a flattened list of weights, while the
TensorFlow format loads based on the object-local names of attributes to
which layers are assigned in the `Model`'s constructor.

#### Arguments:

* <b>`filepath`</b>: String, path to the weights file to load. For weight files in
        TensorFlow format, this is the file prefix (the same as was passed
        to `save_weights`).
* <b>`by_name`</b>: Boolean, whether to load weights by name or by topological
        order. Only topological loading is supported for weight files in
        TensorFlow format.


#### Returns:

When loading a weight file in TensorFlow format, returns the same status
object as <a href="../../tf/train/Checkpoint.md#restore"><code>tf.train.Checkpoint.restore</code></a>. When graph building, restore
ops are run automatically as soon as the network is built (on first call
for user-defined classes inheriting from `Model`, immediately if it is
already built).

When loading weights in HDF5 format, returns `None`.


#### Raises:

* <b>`ImportError`</b>: If h5py is not available and the weight file is in HDF5
        format.

<h3 id="pop"><code>pop</code></h3>

``` python
pop()
```

Removes the last layer in the model.

#### Raises:

* <b>`TypeError`</b>: if there are no layers in the model.

<h3 id="predict"><code>predict</code></h3>

``` python
predict(
    x,
    batch_size=None,
    verbose=0,
    steps=None
)
```

Generates output predictions for the input samples.

Computation is done in batches.

#### Arguments:

x: Input samples. It could be:
 - A Numpy array (or array-like), or a list of arrays
   (in case the model has multiple inputs).
 - A TensorFlow tensor, or a list of tensors
   (in case the model has multiple inputs).
 - A <a href="../../tf/data.md"><code>tf.data</code></a> dataset or a dataset iterator.
* <b>`batch_size`</b>: Integer or `None`.
        Number of samples per gradient update.
        If unspecified, `batch_size` will default to 32.
        Do not specify the `batch_size` is your data is in the
        form of symbolic tensors, dataset, or dataset iterators
        (since they generate batches).
* <b>`verbose`</b>: Verbosity mode, 0 or 1.
* <b>`steps`</b>: Total number of steps (batches of samples)
        before declaring the prediction round finished.
        Ignored with the default value of `None`.


#### Returns:

Numpy array(s) of predictions.


#### Raises:

* <b>`ValueError`</b>: In case of mismatch between the provided
        input data and the model's expectations,
        or in case a stateful model receives a number of samples
        that is not a multiple of the batch size.

<h3 id="predict_classes"><code>predict_classes</code></h3>

``` python
predict_classes(
    x,
    batch_size=32,
    verbose=0
)
```

Generate class predictions for the input samples.

The input samples are processed batch by batch.

#### Arguments:

* <b>`x`</b>: input data, as a Numpy array or list of Numpy arrays
        (if the model has multiple inputs).
* <b>`batch_size`</b>: integer.
* <b>`verbose`</b>: verbosity mode, 0 or 1.


#### Returns:

A numpy array of class predictions.

<h3 id="predict_generator"><code>predict_generator</code></h3>

``` python
predict_generator(
    generator,
    steps=None,
    max_queue_size=10,
    workers=1,
    use_multiprocessing=False,
    verbose=0
)
```

Generates predictions for the input samples from a data generator.

The generator should return the same kind of data as accepted by
`predict_on_batch`.

#### Arguments:

* <b>`generator`</b>: Generator yielding batches of input samples
        or an instance of Sequence (keras.utils.Sequence)
        object in order to avoid duplicate data
        when using multiprocessing.
* <b>`steps`</b>: Total number of steps (batches of samples)
        to yield from `generator` before stopping.
        Optional for `Sequence`: if unspecified, will use
        the `len(generator)` as a number of steps.
* <b>`max_queue_size`</b>: Maximum size for the generator queue.
* <b>`workers`</b>: Integer. Maximum number of processes to spin up
        when using process-based threading.
        If unspecified, `workers` will default to 1. If 0, will
        execute the generator on the main thread.
* <b>`use_multiprocessing`</b>: Boolean.
        If `True`, use process-based threading.
        If unspecified, `use_multiprocessing` will default to `False`.
        Note that because this implementation relies on multiprocessing,
        you should not pass non-picklable arguments to the generator
        as they can't be passed easily to children processes.
* <b>`verbose`</b>: verbosity mode, 0 or 1.


#### Returns:

Numpy array(s) of predictions.


#### Raises:

* <b>`ValueError`</b>: In case the generator yields data in an invalid format.

<h3 id="predict_on_batch"><code>predict_on_batch</code></h3>

``` python
predict_on_batch(x)
```

Returns predictions for a single batch of samples.

#### Arguments:

* <b>`x`</b>: Input data. It could be:
      - A Numpy array (or array-like), or a list of arrays
        (in case the model has multiple inputs).
      - A TensorFlow tensor, or a list of tensors
        (in case the model has multiple inputs).
      - A <a href="../../tf/data.md"><code>tf.data</code></a> dataset or a dataset iterator.


#### Returns:

Numpy array(s) of predictions.


#### Raises:

* <b>`ValueError`</b>: In case of mismatch between given number of inputs and
      expectations of the model.

<h3 id="predict_proba"><code>predict_proba</code></h3>

``` python
predict_proba(
    x,
    batch_size=32,
    verbose=0
)
```

Generates class probability predictions for the input samples.

The input samples are processed batch by batch.

#### Arguments:

* <b>`x`</b>: input data, as a Numpy array or list of Numpy arrays
        (if the model has multiple inputs).
* <b>`batch_size`</b>: integer.
* <b>`verbose`</b>: verbosity mode, 0 or 1.


#### Returns:

A Numpy array of probability predictions.

<h3 id="reset_states"><code>reset_states</code></h3>

``` python
reset_states()
```



<h3 id="save"><code>save</code></h3>

``` python
save(
    filepath,
    overwrite=True,
    include_optimizer=True
)
```

Saves the model to a single HDF5 file.

The savefile includes:
    - The model architecture, allowing to re-instantiate the model.
    - The model weights.
    - The state of the optimizer, allowing to resume training
        exactly where you left off.

This allows you to save the entirety of the state of a model
in a single file.

Saved models can be reinstantiated via `keras.models.load_model`.
The model returned by `load_model`
is a compiled model ready to be used (unless the saved model
was never compiled in the first place).

#### Arguments:

* <b>`filepath`</b>: String, path to the file to save the weights to.
* <b>`overwrite`</b>: Whether to silently overwrite any existing file at the
        target location, or provide the user with a manual prompt.
* <b>`include_optimizer`</b>: If True, save optimizer's state together.

Example:

```python
from keras.models import load_model

model.save('my_model.h5')  # creates a HDF5 file 'my_model.h5'
del model  # deletes the existing model

# returns a compiled model
# identical to the previous one
model = load_model('my_model.h5')
```

<h3 id="save_weights"><code>save_weights</code></h3>

``` python
save_weights(
    filepath,
    overwrite=True,
    save_format=None
)
```

Saves all layer weights.

Either saves in HDF5 or in TensorFlow format based on the `save_format`
argument.

When saving in HDF5 format, the weight file has:
  - `layer_names` (attribute), a list of strings
      (ordered names of model layers).
  - For every layer, a `group` named `layer.name`
      - For every such layer group, a group attribute `weight_names`,
          a list of strings
          (ordered names of weights tensor of the layer).
      - For every weight in the layer, a dataset
          storing the weight value, named after the weight tensor.

When saving in TensorFlow format, all objects referenced by the network are
saved in the same format as <a href="../../tf/train/Checkpoint.md"><code>tf.train.Checkpoint</code></a>, including any `Layer`
instances or `Optimizer` instances assigned to object attributes. For
networks constructed from inputs and outputs using `tf.keras.Model(inputs,
outputs)`, `Layer` instances used by the network are tracked/saved
automatically. For user-defined classes which inherit from <a href="../../tf/keras/Model.md"><code>tf.keras.Model</code></a>,
`Layer` instances must be assigned to object attributes, typically in the
constructor. See the documentation of <a href="../../tf/train/Checkpoint.md"><code>tf.train.Checkpoint</code></a> and
<a href="../../tf/keras/Model.md"><code>tf.keras.Model</code></a> for details.

#### Arguments:

* <b>`filepath`</b>: String, path to the file to save the weights to. When saving
        in TensorFlow format, this is the prefix used for checkpoint files
        (multiple files are generated). Note that the '.h5' suffix causes
        weights to be saved in HDF5 format.
* <b>`overwrite`</b>: Whether to silently overwrite any existing file at the
        target location, or provide the user with a manual prompt.
* <b>`save_format`</b>: Either 'tf' or 'h5'. A `filepath` ending in '.h5' or
        '.keras' will default to HDF5 if `save_format` is `None`. Otherwise
        `None` defaults to 'tf'.


#### Raises:

* <b>`ImportError`</b>: If h5py is not available when attempting to save in HDF5
        format.
* <b>`ValueError`</b>: For invalid/unknown format arguments.

<h3 id="set_weights"><code>set_weights</code></h3>

``` python
set_weights(weights)
```

Sets the weights of the model.

#### Arguments:

* <b>`weights`</b>: A list of Numpy arrays with shapes and types matching
        the output of `model.get_weights()`.

<h3 id="summary"><code>summary</code></h3>

``` python
summary(
    line_length=None,
    positions=None,
    print_fn=None
)
```

Prints a string summary of the network.

#### Arguments:

* <b>`line_length`</b>: Total length of printed lines
        (e.g. set this to adapt the display to different
        terminal window sizes).
* <b>`positions`</b>: Relative or absolute positions of log elements
        in each line. If not provided,
        defaults to `[.33, .55, .67, 1.]`.
* <b>`print_fn`</b>: Print function to use. Defaults to `print`.
        It will be called on each line of the summary.
        You can set it to a custom function
        in order to capture the string summary.


#### Raises:

* <b>`ValueError`</b>: if `summary()` is called before the model is built.

<h3 id="test_on_batch"><code>test_on_batch</code></h3>

``` python
test_on_batch(
    x,
    y=None,
    sample_weight=None
)
```

Test the model on a single batch of samples.

#### Arguments:

* <b>`x`</b>: Input data. It could be:
      - A Numpy array (or array-like), or a list of arrays
        (in case the model has multiple inputs).
      - A TensorFlow tensor, or a list of tensors
        (in case the model has multiple inputs).
      - A dict mapping input names to the corresponding array/tensors,
        if the model has named inputs.
      - A <a href="../../tf/data.md"><code>tf.data</code></a> dataset or a dataset iterator.
* <b>`y`</b>: Target data. Like the input data `x`,
      it could be either Numpy array(s) or TensorFlow tensor(s).
      It should be consistent with `x` (you cannot have Numpy inputs and
      tensor targets, or inversely). If `x` is a dataset or a
      dataset iterator, `y` should not be specified
      (since targets will be obtained from the iterator).
* <b>`sample_weight`</b>: Optional array of the same length as x, containing
        weights to apply to the model's loss for each sample.
        In the case of temporal data, you can pass a 2D array
        with shape (samples, sequence_length),
        to apply a different weight to every timestep of every sample.
        In this case you should make sure to specify
        sample_weight_mode="temporal" in compile(). This argument is not
        supported when `x` is a dataset or a dataset iterator.


#### Returns:

Scalar test loss (if the model has a single output and no metrics)
or list of scalars (if the model has multiple outputs
and/or metrics). The attribute `model.metrics_names` will give you
the display labels for the scalar outputs.


#### Raises:

* <b>`ValueError`</b>: In case of invalid user-provided arguments.

<h3 id="to_json"><code>to_json</code></h3>

``` python
to_json(**kwargs)
```

Returns a JSON string containing the network configuration.

To load a network from a JSON save file, use
`keras.models.model_from_json(json_string, custom_objects={})`.

#### Arguments:

* <b>`**kwargs`</b>: Additional keyword arguments
        to be passed to `json.dumps()`.


#### Returns:

A JSON string.

<h3 id="to_yaml"><code>to_yaml</code></h3>

``` python
to_yaml(**kwargs)
```

Returns a yaml string containing the network configuration.

To load a network from a yaml save file, use
`keras.models.model_from_yaml(yaml_string, custom_objects={})`.

`custom_objects` should be a dictionary mapping
the names of custom losses / layers / etc to the corresponding
functions / classes.

#### Arguments:

* <b>`**kwargs`</b>: Additional keyword arguments
        to be passed to `yaml.dump()`.


#### Returns:

A YAML string.


#### Raises:

* <b>`ImportError`</b>: if yaml module is not found.

<h3 id="train_on_batch"><code>train_on_batch</code></h3>

``` python
train_on_batch(
    x,
    y=None,
    sample_weight=None,
    class_weight=None
)
```

Runs a single gradient update on a single batch of data.

#### Arguments:

* <b>`x`</b>: Input data. It could be:
      - A Numpy array (or array-like), or a list of arrays
        (in case the model has multiple inputs).
      - A TensorFlow tensor, or a list of tensors
        (in case the model has multiple inputs).
      - A dict mapping input names to the corresponding array/tensors,
        if the model has named inputs.
      - A <a href="../../tf/data.md"><code>tf.data</code></a> dataset or a dataset iterator.
* <b>`y`</b>: Target data. Like the input data `x`,
      it could be either Numpy array(s) or TensorFlow tensor(s).
      It should be consistent with `x` (you cannot have Numpy inputs and
      tensor targets, or inversely). If `x` is a dataset or a
      dataset iterator, `y` should not be specified
      (since targets will be obtained from the iterator).
* <b>`sample_weight`</b>: Optional array of the same length as x, containing
        weights to apply to the model's loss for each sample.
        In the case of temporal data, you can pass a 2D array
        with shape (samples, sequence_length),
        to apply a different weight to every timestep of every sample.
        In this case you should make sure to specify
        sample_weight_mode="temporal" in compile(). This argument is not
        supported when `x` is a dataset or a dataset iterator.
* <b>`class_weight`</b>: Optional dictionary mapping
        class indices (integers) to
        a weight (float) to apply to the model's loss for the samples
        from this class during training.
        This can be useful to tell the model to "pay more attention" to
        samples from an under-represented class.


#### Returns:

Scalar training loss
(if the model has a single output and no metrics)
or list of scalars (if the model has multiple outputs
and/or metrics). The attribute `model.metrics_names` will give you
the display labels for the scalar outputs.


#### Raises:

* <b>`ValueError`</b>: In case of invalid user-provided arguments.




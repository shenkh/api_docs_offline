<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.RNN" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="activity_regularizer"/>
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="dynamic"/>
<meta itemprop="property" content="input"/>
<meta itemprop="property" content="input_mask"/>
<meta itemprop="property" content="input_shape"/>
<meta itemprop="property" content="input_spec"/>
<meta itemprop="property" content="losses"/>
<meta itemprop="property" content="metrics"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="name_scope"/>
<meta itemprop="property" content="non_trainable_variables"/>
<meta itemprop="property" content="non_trainable_weights"/>
<meta itemprop="property" content="output"/>
<meta itemprop="property" content="output_mask"/>
<meta itemprop="property" content="output_shape"/>
<meta itemprop="property" content="states"/>
<meta itemprop="property" content="submodules"/>
<meta itemprop="property" content="trainable"/>
<meta itemprop="property" content="trainable_variables"/>
<meta itemprop="property" content="trainable_weights"/>
<meta itemprop="property" content="updates"/>
<meta itemprop="property" content="variables"/>
<meta itemprop="property" content="weights"/>
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__delattr__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__setattr__"/>
<meta itemprop="property" content="build"/>
<meta itemprop="property" content="compute_mask"/>
<meta itemprop="property" content="compute_output_shape"/>
<meta itemprop="property" content="count_params"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
<meta itemprop="property" content="get_initial_state"/>
<meta itemprop="property" content="get_input_at"/>
<meta itemprop="property" content="get_input_mask_at"/>
<meta itemprop="property" content="get_input_shape_at"/>
<meta itemprop="property" content="get_losses_for"/>
<meta itemprop="property" content="get_output_at"/>
<meta itemprop="property" content="get_output_mask_at"/>
<meta itemprop="property" content="get_output_shape_at"/>
<meta itemprop="property" content="get_updates_for"/>
<meta itemprop="property" content="get_weights"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="set_weights"/>
<meta itemprop="property" content="with_name_scope"/>
</div>

# tf.keras.layers.RNN

## Class `RNN`

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)



Defined in [`tensorflow/python/keras/layers/recurrent.py`](/code/stable/tensorflow/python/keras/layers/recurrent.py).

Base class for recurrent layers.

#### Arguments:

* <b>`cell`</b>: A RNN cell instance or a list of RNN cell instances.
    A RNN cell is a class that has:
    - A `call(input_at_t, states_at_t)` method, returning
      `(output_at_t, states_at_t_plus_1)`. The call method of the
      cell can also take the optional argument `constants`, see
      section "Note on passing external constants" below.
    - A `state_size` attribute. This can be a single integer
      (single state) in which case it is the size of the recurrent
      state. This can also be a list/tuple of integers (one size per
      state).
      The `state_size` can also be TensorShape or tuple/list of
      TensorShape, to represent high dimension state.
    - A `output_size` attribute. This can be a single integer or a
      TensorShape, which represent the shape of the output. For backward
      compatible reason, if this attribute is not available for the
      cell, the value will be inferred by the first element of the
      `state_size`.
    - A `get_initial_state(inputs=None, batch_size=None, dtype=None)`
      method that creates a tensor meant to be fed to `call()` as the
      initial state, if the user didn't specify any initial state via other
      means. The returned initial state should have a shape of
      [batch_size, cell.state_size]. The cell might choose to create a
      tensor full of zeros, or full of other values based on the cell's
      implementation.
      `inputs` is the input tensor to the RNN layer, which should
      contain the batch size as its shape[0], and also dtype. Note that
      the shape[0] might be `None` during the graph construction. Either
      the `inputs` or the pair of `batch_size` and `dtype` are provided.
      `batch_size` is a scalar tensor that represents the batch size
      of the inputs. `dtype` is <a href="../../../tf/dtypes/DType.md"><code>tf.DType</code></a> that represents the dtype of
      the inputs.
      For backward compatible reason, if this method is not implemented
      by the cell, the RNN layer will create a zero filled tensor with the
      size of [batch_size, cell.state_size].
    In the case that `cell` is a list of RNN cell instances, the cells
    will be stacked on top of each other in the RNN, resulting in an
    efficient stacked RNN.
* <b>`return_sequences`</b>: Boolean. Whether to return the last output
    in the output sequence, or the full sequence.
* <b>`return_state`</b>: Boolean. Whether to return the last state
    in addition to the output.
* <b>`go_backwards`</b>: Boolean (default False).
    If True, process the input sequence backwards and return the
    reversed sequence.
* <b>`stateful`</b>: Boolean (default False). If True, the last state
    for each sample at index i in a batch will be used as initial
    state for the sample of index i in the following batch.
* <b>`unroll`</b>: Boolean (default False).
    If True, the network will be unrolled, else a symbolic loop will be used.
    Unrolling can speed-up a RNN,
    although it tends to be more memory-intensive.
    Unrolling is only suitable for short sequences.
* <b>`time_major`</b>: The shape format of the `inputs` and `outputs` tensors.
    If True, the inputs and outputs will be in shape
    `(timesteps, batch, ...)`, whereas in the False case, it will be
    `(batch, timesteps, ...)`. Using `time_major = True` is a bit more
    efficient because it avoids transposes at the beginning and end of the
    RNN calculation. However, most TensorFlow data is batch-major, so by
    default this function accepts input and emits output in batch-major
    form.

Call arguments:
* <b>`inputs`</b>: Input tensor.
* <b>`mask`</b>: Binary tensor of shape `(samples, timesteps)` indicating whether
    a given timestep should be masked.
* <b>`training`</b>: Python boolean indicating whether the layer should behave in
    training mode or in inference mode. This argument is passed to the cell
    when calling it. This is for use with cells that use dropout.
* <b>`initial_state`</b>: List of initial state tensors to be passed to the first
    call of the cell.
* <b>`constants`</b>: List of constant tensors to be passed to the cell at each
    timestep.

Input shape:
  N-D tensor with shape `(batch_size, timesteps, ...)` or
  `(timesteps, batch_size, ...)` when time_major is True.

Output shape:
  - If `return_state`: a list of tensors. The first tensor is
    the output. The remaining tensors are the last states,
    each with shape `(batch_size, state_size)`, where `state_size` could
    be a high dimension tensor shape.
  - If `return_sequences`: N-D tensor with shape
    `(batch_size, timesteps, output_size)`, where `output_size` could
    be a high dimension tensor shape, or
    `(timesteps, batch_size, output_size)` when `time_major` is True.
  - Else, N-D tensor with shape `(batch_size, output_size)`, where
    `output_size` could be a high dimension tensor shape.

Masking:
  This layer supports masking for input data with a variable number
  of timesteps. To introduce masks to your data,
  use an [Embedding](embeddings.md) layer with the `mask_zero` parameter
  set to `True`.

Note on using statefulness in RNNs:
  You can set RNN layers to be 'stateful', which means that the states
  computed for the samples in one batch will be reused as initial states
  for the samples in the next batch. This assumes a one-to-one mapping
  between samples in different successive batches.

  To enable statefulness:
    - Specify `stateful=True` in the layer constructor.
    - Specify a fixed batch size for your model, by passing
      If sequential model:
        `batch_input_shape=(...)` to the first layer in your model.
      Else for functional model with 1 or more Input layers:
        `batch_shape=(...)` to all the first layers in your model.
      This is the expected shape of your inputs
      *including the batch size*.
      It should be a tuple of integers, e.g. `(32, 10, 100)`.
    - Specify `shuffle=False` when calling fit().

  To reset the states of your model, call `.reset_states()` on either
  a specific layer, or on your entire model.

Note on specifying the initial state of RNNs:
  You can specify the initial state of RNN layers symbolically by
  calling them with the keyword argument `initial_state`. The value of
  `initial_state` should be a tensor or list of tensors representing
  the initial state of the RNN layer.

  You can specify the initial state of RNN layers numerically by
  calling `reset_states` with the keyword argument `states`. The value of
  `states` should be a numpy array or list of numpy arrays representing
  the initial state of the RNN layer.

Note on passing external constants to RNNs:
  You can pass "external" constants to the cell using the `constants`
  keyword argument of `RNN.__call__` (as well as `RNN.call`) method. This
  requires that the `cell.call` method accepts the same keyword argument
  `constants`. Such constants can be used to condition the cell
  transformation on additional static inputs (not changing over time),
  a.k.a. an attention mechanism.

Examples:

```python
# First, let's define a RNN Cell, as a layer subclass.

class MinimalRNNCell(keras.layers.Layer):

    def __init__(self, units, **kwargs):
        self.units = units
        self.state_size = units
        super(MinimalRNNCell, self).__init__(**kwargs)

    def build(self, input_shape):
        self.kernel = self.add_weight(shape=(input_shape[-1], self.units),
                                      initializer='uniform',
                                      name='kernel')
        self.recurrent_kernel = self.add_weight(
            shape=(self.units, self.units),
            initializer='uniform',
            name='recurrent_kernel')
        self.built = True

    def call(self, inputs, states):
        prev_output = states[0]
        h = K.dot(inputs, self.kernel)
        output = h + K.dot(prev_output, self.recurrent_kernel)
        return output, [output]

# Let's use this cell in a RNN layer:

cell = MinimalRNNCell(32)
x = keras.Input((None, 5))
layer = RNN(cell)
y = layer(x)

# Here's how to use the cell to build a stacked RNN:

cells = [MinimalRNNCell(32), MinimalRNNCell(64)]
x = keras.Input((None, 5))
layer = RNN(cells)
y = layer(x)
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    cell,
    return_sequences=False,
    return_state=False,
    go_backwards=False,
    stateful=False,
    unroll=False,
    time_major=False,
    **kwargs
)
```





## Properties

<h3 id="activity_regularizer"><code>activity_regularizer</code></h3>

Optional regularizer function for the output of this layer.

<h3 id="dtype"><code>dtype</code></h3>



<h3 id="dynamic"><code>dynamic</code></h3>



<h3 id="input"><code>input</code></h3>

Retrieves the input tensor(s) of a layer.

Only applicable if the layer has exactly one input,
i.e. if it is connected to one incoming layer.

#### Returns:

Input tensor or list of input tensors.


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



<h3 id="losses"><code>losses</code></h3>

Losses which are associated with this `Layer`.

Variable regularization tensors are created when this property is accessed,
so it is eager safe: accessing `losses` under a <a href="../../../tf/GradientTape.md"><code>tf.GradientTape</code></a> will
propagate gradients back to the corresponding variables.

#### Returns:

A list of tensors.

<h3 id="metrics"><code>metrics</code></h3>



<h3 id="name"><code>name</code></h3>

Returns the name of this module as passed or determined in the ctor.

NOTE: This is not the same as the `self.name_scope.name` which includes
parent module names.

<h3 id="name_scope"><code>name_scope</code></h3>

Returns a <a href="../../../tf/name_scope.md"><code>tf.name_scope</code></a> instance for this class.

<h3 id="non_trainable_variables"><code>non_trainable_variables</code></h3>



<h3 id="non_trainable_weights"><code>non_trainable_weights</code></h3>



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

<h3 id="states"><code>states</code></h3>



<h3 id="submodules"><code>submodules</code></h3>

Sequence of all sub-modules.

Submodules are modules which are properties of this module, or found as
properties of modules which are properties of this module (and so on).

```
a = tf.Module()
b = tf.Module()
c = tf.Module()
a.b = b
b.c = c
assert list(a.submodules) == [b, c]
assert list(b.submodules) == [c]
assert list(c.submodules) == []
```

#### Returns:

A sequence of all submodules.

<h3 id="trainable"><code>trainable</code></h3>



<h3 id="trainable_variables"><code>trainable_variables</code></h3>

Sequence of variables owned by this module and it's submodules.

Note: this method uses reflection to find variables on the current instance
and submodules. For performance reasons you may wish to cache the result
of calling this method if you don't expect the return value to change.

#### Returns:

A sequence of variables for the current module (sorted by attribute
name) followed by variables from all submodules recursively (breadth
first).

<h3 id="trainable_weights"><code>trainable_weights</code></h3>



<h3 id="updates"><code>updates</code></h3>



<h3 id="variables"><code>variables</code></h3>

Returns the list of all layer variables/weights.

Alias of `self.weights`.

#### Returns:

A list of variables.

<h3 id="weights"><code>weights</code></h3>

Returns the list of all layer variables/weights.

#### Returns:

A list of variables.



## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    inputs,
    initial_state=None,
    constants=None,
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

<h3 id="__delattr__"><code>__delattr__</code></h3>

``` python
__delattr__(name)
```

Implement delattr(self, name).

<h3 id="__setattr__"><code>__setattr__</code></h3>

``` python
__setattr__(
    name,
    value
)
```

Support self.foo = trackable syntax.

<h3 id="build"><code>build</code></h3>

``` python
build(input_shape)
```

Creates the variables of the layer (optional, for subclass implementers).

This is a method that implementers of subclasses of `Layer` or `Model`
can override if they need a state-creation step in-between
layer instantiation and layer call.

This is typically used to create the weights of `Layer` subclasses.

#### Arguments:

* <b>`input_shape`</b>: Instance of `TensorShape`, or list of instances of
    `TensorShape` if the layer expects a list of inputs
    (one instance per input).

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

If the layer has not been built, this method will call `build` on the
layer. This assumes that the layer will later be used with inputs that
match the input shape provided here.

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

<h3 id="from_config"><code>from_config</code></h3>

``` python
@classmethod
from_config(
    cls,
    config,
    custom_objects=None
)
```

Creates a layer from its config.

This method is the reverse of `get_config`,
capable of instantiating the same layer from the config
dictionary. It does not handle layer connectivity
(handled by Network), nor weights (handled by `set_weights`).

#### Arguments:

* <b>`config`</b>: A Python dictionary, typically the
        output of get_config.


#### Returns:

A layer instance.

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

<h3 id="get_initial_state"><code>get_initial_state</code></h3>

``` python
get_initial_state(inputs)
```



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

<h3 id="get_losses_for"><code>get_losses_for</code></h3>

``` python
get_losses_for(inputs)
```

Retrieves losses relevant to a specific set of inputs.

#### Arguments:

* <b>`inputs`</b>: Input tensor or list/tuple of input tensors.


#### Returns:

List of loss tensors of the layer that depend on `inputs`.

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

<h3 id="get_weights"><code>get_weights</code></h3>

``` python
get_weights()
```

Returns the current weights of the layer.

#### Returns:

Weights values as a list of numpy arrays.

<h3 id="reset_states"><code>reset_states</code></h3>

``` python
reset_states(states=None)
```



<h3 id="set_weights"><code>set_weights</code></h3>

``` python
set_weights(weights)
```

Sets the weights of the layer, from Numpy arrays.

#### Arguments:

* <b>`weights`</b>: a list of Numpy arrays. The number
        of arrays and their shape must match
        number of the dimensions of the weights
        of the layer (i.e. it should match the
        output of `get_weights`).


#### Raises:

* <b>`ValueError`</b>: If the provided weights list does not match the
        layer's specifications.

<h3 id="with_name_scope"><code>with_name_scope</code></h3>

``` python
with_name_scope(
    cls,
    method
)
```

Decorator to automatically enter the module name scope.

```
class MyModule(tf.Module):
  @tf.Module.with_name_scope
  def __call__(self, x):
    if not hasattr(self, 'w'):
      self.w = tf.Variable(tf.random.normal([x.shape[1], 64]))
    return tf.matmul(x, self.w)
```

Using the above module would produce <a href="../../../tf/Variable.md"><code>tf.Variable</code></a>s and <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>s whose
names included the module name:

```
mod = MyModule()
mod(tf.ones([8, 32]))
# ==> <tf.Tensor: ...>
mod.w
# ==> <tf.Variable ...'my_module/w:0'>
```

#### Args:

* <b>`method`</b>: The method to wrap.


#### Returns:

The original method wrapped such that it enters the module's name scope.




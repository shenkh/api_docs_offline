<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.ConvLSTM2D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="activation"/>
<meta itemprop="property" content="activity_regularizer"/>
<meta itemprop="property" content="bias_constraint"/>
<meta itemprop="property" content="bias_initializer"/>
<meta itemprop="property" content="bias_regularizer"/>
<meta itemprop="property" content="data_format"/>
<meta itemprop="property" content="dilation_rate"/>
<meta itemprop="property" content="dropout"/>
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="dynamic"/>
<meta itemprop="property" content="filters"/>
<meta itemprop="property" content="input"/>
<meta itemprop="property" content="input_mask"/>
<meta itemprop="property" content="input_shape"/>
<meta itemprop="property" content="input_spec"/>
<meta itemprop="property" content="kernel_constraint"/>
<meta itemprop="property" content="kernel_initializer"/>
<meta itemprop="property" content="kernel_regularizer"/>
<meta itemprop="property" content="kernel_size"/>
<meta itemprop="property" content="losses"/>
<meta itemprop="property" content="metrics"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="name_scope"/>
<meta itemprop="property" content="non_trainable_variables"/>
<meta itemprop="property" content="non_trainable_weights"/>
<meta itemprop="property" content="output"/>
<meta itemprop="property" content="output_mask"/>
<meta itemprop="property" content="output_shape"/>
<meta itemprop="property" content="padding"/>
<meta itemprop="property" content="recurrent_activation"/>
<meta itemprop="property" content="recurrent_constraint"/>
<meta itemprop="property" content="recurrent_dropout"/>
<meta itemprop="property" content="recurrent_initializer"/>
<meta itemprop="property" content="recurrent_regularizer"/>
<meta itemprop="property" content="states"/>
<meta itemprop="property" content="strides"/>
<meta itemprop="property" content="submodules"/>
<meta itemprop="property" content="trainable"/>
<meta itemprop="property" content="trainable_variables"/>
<meta itemprop="property" content="trainable_weights"/>
<meta itemprop="property" content="unit_forget_bias"/>
<meta itemprop="property" content="updates"/>
<meta itemprop="property" content="use_bias"/>
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

# tf.keras.layers.ConvLSTM2D

## Class `ConvLSTM2D`





Defined in [`tensorflow/python/keras/layers/convolutional_recurrent.py`](/code/stable/tensorflow/python/keras/layers/convolutional_recurrent.py).

Convolutional LSTM.

It is similar to an LSTM layer, but the input transformations
and recurrent transformations are both convolutional.

#### Arguments:

* <b>`filters`</b>: Integer, the dimensionality of the output space
    (i.e. the number of output filters in the convolution).
* <b>`kernel_size`</b>: An integer or tuple/list of n integers, specifying the
    dimensions of the convolution window.
* <b>`strides`</b>: An integer or tuple/list of n integers,
    specifying the strides of the convolution.
    Specifying any stride value != 1 is incompatible with specifying
    any `dilation_rate` value != 1.
* <b>`padding`</b>: One of `"valid"` or `"same"` (case-insensitive).
* <b>`data_format`</b>: A string,
    one of `channels_last` (default) or `channels_first`.
    The ordering of the dimensions in the inputs.
    `channels_last` corresponds to inputs with shape
    `(batch, time, ..., channels)`
    while `channels_first` corresponds to
    inputs with shape `(batch, time, channels, ...)`.
    It defaults to the `image_data_format` value found in your
    Keras config file at `~/.keras/keras.json`.
    If you never set it, then it will be "channels_last".
* <b>`dilation_rate`</b>: An integer or tuple/list of n integers, specifying
    the dilation rate to use for dilated convolution.
    Currently, specifying any `dilation_rate` value != 1 is
    incompatible with specifying any `strides` value != 1.
* <b>`activation`</b>: Activation function to use.
    By default hyperbolic tangent activation function is applied
    (`tanh(x)`).
* <b>`recurrent_activation`</b>: Activation function to use
    for the recurrent step.
* <b>`use_bias`</b>: Boolean, whether the layer uses a bias vector.
* <b>`kernel_initializer`</b>: Initializer for the `kernel` weights matrix,
    used for the linear transformation of the inputs.
* <b>`recurrent_initializer`</b>: Initializer for the `recurrent_kernel`
    weights matrix,
    used for the linear transformation of the recurrent state.
* <b>`bias_initializer`</b>: Initializer for the bias vector.
* <b>`unit_forget_bias`</b>: Boolean.
    If True, add 1 to the bias of the forget gate at initialization.
    Use in combination with `bias_initializer="zeros"`.
    This is recommended in [Jozefowicz et al.]
    (http://www.jmlr.org/proceedings/papers/v37/jozefowicz15.pdf)
* <b>`kernel_regularizer`</b>: Regularizer function applied to
    the `kernel` weights matrix.
* <b>`recurrent_regularizer`</b>: Regularizer function applied to
    the `recurrent_kernel` weights matrix.
* <b>`bias_regularizer`</b>: Regularizer function applied to the bias vector.
* <b>`activity_regularizer`</b>: Regularizer function applied to.
* <b>`kernel_constraint`</b>: Constraint function applied to
    the `kernel` weights matrix.
* <b>`recurrent_constraint`</b>: Constraint function applied to
    the `recurrent_kernel` weights matrix.
* <b>`bias_constraint`</b>: Constraint function applied to the bias vector.
* <b>`return_sequences`</b>: Boolean. Whether to return the last output
    in the output sequence, or the full sequence.
* <b>`go_backwards`</b>: Boolean (default False).
    If True, process the input sequence backwards.
* <b>`stateful`</b>: Boolean (default False). If True, the last state
    for each sample at index i in a batch will be used as initial
    state for the sample of index i in the following batch.
* <b>`dropout`</b>: Float between 0 and 1.
    Fraction of the units to drop for
    the linear transformation of the inputs.
* <b>`recurrent_dropout`</b>: Float between 0 and 1.
    Fraction of the units to drop for
    the linear transformation of the recurrent state.

Call arguments:
* <b>`inputs`</b>: A 5D tensor.
* <b>`mask`</b>: Binary tensor of shape `(samples, timesteps)` indicating whether
    a given timestep should be masked.
* <b>`training`</b>: Python boolean indicating whether the layer should behave in
    training mode or in inference mode. This argument is passed to the cell
    when calling it. This is only relevant if `dropout` or `recurrent_dropout`
    are set.
* <b>`initial_state`</b>: List of initial state tensors to be passed to the first
    call of the cell.

Input shape:
  - If data_format='channels_first'
      5D tensor with shape:
      `(samples, time, channels, rows, cols)`
  - If data_format='channels_last'
      5D tensor with shape:
      `(samples, time, rows, cols, channels)`

Output shape:
  - If `return_sequences`
     - If data_format='channels_first'
        5D tensor with shape:
        `(samples, time, filters, output_row, output_col)`
     - If data_format='channels_last'
        5D tensor with shape:
        `(samples, time, output_row, output_col, filters)`
  - Else
    - If data_format ='channels_first'
        4D tensor with shape:
        `(samples, filters, output_row, output_col)`
    - If data_format='channels_last'
        4D tensor with shape:
        `(samples, output_row, output_col, filters)`
    where `o_row` and `o_col` depend on the shape of the filter and
    the padding


#### Raises:

* <b>`ValueError`</b>: in case of invalid constructor arguments.

References:
  - [Convolutional LSTM Network: A Machine Learning Approach for
  Precipitation Nowcasting](http://arxiv.org/abs/1506.04214v1)
  The current implementation does not include the feedback loop on the
  cells output.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    filters,
    kernel_size,
    strides=(1, 1),
    padding='valid',
    data_format=None,
    dilation_rate=(1, 1),
    activation='tanh',
    recurrent_activation='hard_sigmoid',
    use_bias=True,
    kernel_initializer='glorot_uniform',
    recurrent_initializer='orthogonal',
    bias_initializer='zeros',
    unit_forget_bias=True,
    kernel_regularizer=None,
    recurrent_regularizer=None,
    bias_regularizer=None,
    activity_regularizer=None,
    kernel_constraint=None,
    recurrent_constraint=None,
    bias_constraint=None,
    return_sequences=False,
    go_backwards=False,
    stateful=False,
    dropout=0.0,
    recurrent_dropout=0.0,
    **kwargs
)
```





## Properties

<h3 id="activation"><code>activation</code></h3>



<h3 id="activity_regularizer"><code>activity_regularizer</code></h3>

Optional regularizer function for the output of this layer.

<h3 id="bias_constraint"><code>bias_constraint</code></h3>



<h3 id="bias_initializer"><code>bias_initializer</code></h3>



<h3 id="bias_regularizer"><code>bias_regularizer</code></h3>



<h3 id="data_format"><code>data_format</code></h3>



<h3 id="dilation_rate"><code>dilation_rate</code></h3>



<h3 id="dropout"><code>dropout</code></h3>



<h3 id="dtype"><code>dtype</code></h3>



<h3 id="dynamic"><code>dynamic</code></h3>



<h3 id="filters"><code>filters</code></h3>



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



<h3 id="kernel_constraint"><code>kernel_constraint</code></h3>



<h3 id="kernel_initializer"><code>kernel_initializer</code></h3>



<h3 id="kernel_regularizer"><code>kernel_regularizer</code></h3>



<h3 id="kernel_size"><code>kernel_size</code></h3>



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

<h3 id="padding"><code>padding</code></h3>



<h3 id="recurrent_activation"><code>recurrent_activation</code></h3>



<h3 id="recurrent_constraint"><code>recurrent_constraint</code></h3>



<h3 id="recurrent_dropout"><code>recurrent_dropout</code></h3>



<h3 id="recurrent_initializer"><code>recurrent_initializer</code></h3>



<h3 id="recurrent_regularizer"><code>recurrent_regularizer</code></h3>



<h3 id="states"><code>states</code></h3>



<h3 id="strides"><code>strides</code></h3>



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



<h3 id="unit_forget_bias"><code>unit_forget_bias</code></h3>



<h3 id="updates"><code>updates</code></h3>



<h3 id="use_bias"><code>use_bias</code></h3>



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
build(
    instance,
    input_shape
)
```



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
compute_output_shape(
    instance,
    input_shape
)
```



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
    config
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




<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Bidirectional" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="activity_regularizer"/>
<meta itemprop="property" content="constraints"/>
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

# tf.keras.layers.Bidirectional

## Class `Bidirectional`

Inherits From: [`Wrapper`](../../../tf/keras/layers/Wrapper.md)



Defined in [`tensorflow/python/keras/layers/wrappers.py`](/code/stable/tensorflow/python/keras/layers/wrappers.py).

Bidirectional wrapper for RNNs.

#### Arguments:

* <b>`layer`</b>: `Recurrent` instance.
* <b>`merge_mode`</b>: Mode by which outputs of the
    forward and backward RNNs will be combined.
    One of {'sum', 'mul', 'concat', 'ave', None}.
    If None, the outputs will not be combined,
    they will be returned as a list.
* <b>`backward_layer`</b>: Optional `Recurrent` instance to be used to handle
    backwards input processing. If `backward_layer` is not provided,
    the layer instance passed as the `layer` argument will be used to
    generate the backward layer automatically.
    Note that the provided `backward_layer` layer should have properties
    matching those of the `layer` argument, in particular it should have the
    same values for `stateful`, `return_states`, `return_sequence`, etc.
    In addition, `backward_layer` and `layer` should have
    different `go_backwards` argument values.
    A `ValueError` will be raised if these requirements are not met.

Call arguments:
  The call arguments for this layer are the same as those of the wrapped RNN
    layer.


#### Raises:

* <b>`ValueError`</b>:     1. If `layer` or `backward_layer` is not a `Layer` instance.
    2. In case of invalid `merge_mode` argument.
    3. If `backward_layer` has mismatched properties compared to `layer`.

Examples:

```python
model = Sequential()
model.add(Bidirectional(LSTM(10, return_sequences=True), input_shape=(5, 10)))
model.add(Bidirectional(LSTM(10)))
model.add(Dense(5))
model.add(Activation('softmax'))
model.compile(loss='categorical_crossentropy', optimizer='rmsprop')

 # With custom backward layer
 model = Sequential()
 forward_layer = LSTM(10, return_sequences=True)
 backard_layer = LSTM(10, activation='relu', return_sequences=True,
                      go_backwards=True)
 model.add(Bidirectional(forward_layer, backward_layer=backward_layer,
                         input_shape=(5, 10)))
 model.add(Dense(5))
 model.add(Activation('softmax'))
 model.compile(loss='categorical_crossentropy', optimizer='rmsprop')
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    layer,
    merge_mode='concat',
    weights=None,
    backward_layer=None,
    **kwargs
)
```





## Properties

<h3 id="activity_regularizer"><code>activity_regularizer</code></h3>

Optional regularizer function for the output of this layer.

<h3 id="constraints"><code>constraints</code></h3>



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

`Bidirectional.__call__` implements the same API as the wrapped `RNN`.

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
reset_states()
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




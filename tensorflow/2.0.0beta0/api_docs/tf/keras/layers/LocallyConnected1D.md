<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.LocallyConnected1D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.LocallyConnected1D

## Class `LocallyConnected1D`

Locally-connected layer for 1D inputs.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

### Aliases:

* Class `tf.compat.v1.keras.layers.LocallyConnected1D`
* Class `tf.compat.v2.keras.layers.LocallyConnected1D`
* Class `tf.keras.layers.LocallyConnected1D`



Defined in [`python/keras/layers/local.py`](/code/stable/tensorflow/python/keras/layers/local.py).

<!-- Placeholder for "Used in" -->

The `LocallyConnected1D` layer works similarly to
the `Conv1D` layer, except that weights are unshared,
that is, a different set of filters is applied at each different patch
of the input.

#### Example:


```python
    # apply a unshared weight convolution 1d of length 3 to a sequence with
    # 10 timesteps, with 64 output filters
    model = Sequential()
    model.add(LocallyConnected1D(64, 3, input_shape=(10, 32)))
    # now model.output_shape == (None, 8, 64)
    # add a new conv1d on top
    model.add(LocallyConnected1D(32, 3))
    # now model.output_shape == (None, 6, 32)
```

#### Arguments:


* <b>`filters`</b>: Integer, the dimensionality of the output space
    (i.e. the number of output filters in the convolution).
* <b>`kernel_size`</b>: An integer or tuple/list of a single integer,
    specifying the length of the 1D convolution window.
* <b>`strides`</b>: An integer or tuple/list of a single integer,
    specifying the stride length of the convolution.
    Specifying any stride value != 1 is incompatible with specifying
    any `dilation_rate` value != 1.
* <b>`padding`</b>: Currently only supports `"valid"` (case-insensitive).
    `"same"` may be supported in the future.
* <b>`data_format`</b>: A string,
    one of `channels_last` (default) or `channels_first`.
    The ordering of the dimensions in the inputs.
    `channels_last` corresponds to inputs with shape
    `(batch, length, channels)` while `channels_first`
    corresponds to inputs with shape
    `(batch, channels, length)`.
    It defaults to the `image_data_format` value found in your
    Keras config file at `~/.keras/keras.json`.
    If you never set it, then it will be "channels_last".
* <b>`activation`</b>: Activation function to use.
    If you don't specify anything, no activation is applied
    (ie. "linear" activation: `a(x) = x`).
* <b>`use_bias`</b>: Boolean, whether the layer uses a bias vector.
* <b>`kernel_initializer`</b>: Initializer for the `kernel` weights matrix.
* <b>`bias_initializer`</b>: Initializer for the bias vector.
* <b>`kernel_regularizer`</b>: Regularizer function applied to
    the `kernel` weights matrix.
* <b>`bias_regularizer`</b>: Regularizer function applied to the bias vector.
* <b>`activity_regularizer`</b>: Regularizer function applied to
    the output of the layer (its "activation")..
* <b>`kernel_constraint`</b>: Constraint function applied to the kernel matrix.
* <b>`bias_constraint`</b>: Constraint function applied to the bias vector.
* <b>`implementation`</b>: implementation mode, either `1` or `2`.
    `1` loops over input spatial locations to perform the forward pass.
    It is memory-efficient but performs a lot of (small) ops.

    `2` stores layer weights in a dense but sparsely-populated 2D matrix
    and implements the forward pass as a single matrix-multiply. It uses
    a lot of RAM but performs few (large) ops.

    Depending on the inputs, layer parameters, hardware, and
    `tf.executing_eagerly()` one implementation can be dramatically faster
    (e.g. 50X) than another.

    It is recommended to benchmark both in the setting of interest to pick
    the most efficient one (in terms of speed and memory usage).

    Following scenarios could benefit from setting `implementation=2`:
        - eager execution;
        - inference;
        - running on CPU;
        - large amount of RAM available;
        - small models (few filters, small kernel);
        - using `padding=same` (only possible with `implementation=2`).


#### Input shape:

3D tensor with shape: `(batch_size, steps, input_dim)`



#### Output shape:

3D tensor with shape: `(batch_size, new_steps, filters)`
`steps` value might have changed due to padding or strides.


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    filters,
    kernel_size,
    strides=1,
    padding='valid',
    data_format=None,
    activation=None,
    use_bias=True,
    kernel_initializer='glorot_uniform',
    bias_initializer='zeros',
    kernel_regularizer=None,
    bias_regularizer=None,
    activity_regularizer=None,
    kernel_constraint=None,
    bias_constraint=None,
    implementation=1,
    **kwargs
)
```







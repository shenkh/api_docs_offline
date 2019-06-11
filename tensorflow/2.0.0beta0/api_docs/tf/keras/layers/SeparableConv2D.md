<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.SeparableConv2D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.SeparableConv2D

## Class `SeparableConv2D`

Depthwise separable 2D convolution.



### Aliases:

* Class `tf.compat.v1.keras.layers.SeparableConv2D`
* Class `tf.compat.v1.keras.layers.SeparableConvolution2D`
* Class `tf.compat.v2.keras.layers.SeparableConv2D`
* Class `tf.compat.v2.keras.layers.SeparableConvolution2D`
* Class `tf.keras.layers.SeparableConv2D`
* Class `tf.keras.layers.SeparableConvolution2D`



Defined in [`python/keras/layers/convolutional.py`](/code/stable/tensorflow/python/keras/layers/convolutional.py).

<!-- Placeholder for "Used in" -->

Separable convolutions consist in first performing
a depthwise spatial convolution
(which acts on each input channel separately)
followed by a pointwise convolution which mixes together the resulting
output channels. The `depth_multiplier` argument controls how many
output channels are generated per input channel in the depthwise step.

Intuitively, separable convolutions can be understood as
a way to factorize a convolution kernel into two smaller kernels,
or as an extreme version of an Inception block.

#### Arguments:


* <b>`filters`</b>: Integer, the dimensionality of the output space
  (i.e. the number of output filters in the convolution).
* <b>`kernel_size`</b>: An integer or tuple/list of 2 integers, specifying the
  height and width of the 2D convolution window.
  Can be a single integer to specify the same value for
  all spatial dimensions.
* <b>`strides`</b>: An integer or tuple/list of 2 integers,
  specifying the strides of the convolution along the height and width.
  Can be a single integer to specify the same value for
  all spatial dimensions.
  Specifying any stride value != 1 is incompatible with specifying
  any `dilation_rate` value != 1.
* <b>`padding`</b>: one of `"valid"` or `"same"` (case-insensitive).
* <b>`data_format`</b>: A string,
  one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch, height, width, channels)` while `channels_first`
  corresponds to inputs with shape
  `(batch, channels, height, width)`.
  It defaults to the `image_data_format` value found in your
  Keras config file at `~/.keras/keras.json`.
  If you never set it, then it will be "channels_last".
* <b>`dilation_rate`</b>: An integer or tuple/list of 2 integers, specifying
  the dilation rate to use for dilated convolution.
  Currently, specifying any `dilation_rate` value != 1 is
  incompatible with specifying any `strides` value != 1.
* <b>`depth_multiplier`</b>: The number of depthwise convolution output channels
  for each input channel.
  The total number of depthwise convolution output
  channels will be equal to `filters_in * depth_multiplier`.
* <b>`activation`</b>: Activation function to use.
  If you don't specify anything, no activation is applied
  (ie. "linear" activation: `a(x) = x`).
* <b>`use_bias`</b>: Boolean, whether the layer uses a bias vector.
* <b>`depthwise_initializer`</b>: Initializer for the depthwise kernel matrix.
* <b>`pointwise_initializer`</b>: Initializer for the pointwise kernel matrix.
* <b>`bias_initializer`</b>: Initializer for the bias vector.
* <b>`depthwise_regularizer`</b>: Regularizer function applied to
  the depthwise kernel matrix.
* <b>`pointwise_regularizer`</b>: Regularizer function applied to
  the pointwise kernel matrix.
* <b>`bias_regularizer`</b>: Regularizer function applied to the bias vector.
* <b>`activity_regularizer`</b>: Regularizer function applied to
  the output of the layer (its "activation")..
* <b>`depthwise_constraint`</b>: Constraint function applied to
  the depthwise kernel matrix.
* <b>`pointwise_constraint`</b>: Constraint function applied to
  the pointwise kernel matrix.
* <b>`bias_constraint`</b>: Constraint function applied to the bias vector.


#### Input shape:

4D tensor with shape:
`(batch, channels, rows, cols)` if data_format='channels_first'
or 4D tensor with shape:
`(batch, rows, cols, channels)` if data_format='channels_last'.



#### Output shape:

4D tensor with shape:
`(batch, filters, new_rows, new_cols)` if data_format='channels_first'
or 4D tensor with shape:
`(batch, new_rows, new_cols, filters)` if data_format='channels_last'.
`rows` and `cols` values might have changed due to padding.


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    filters,
    kernel_size,
    strides=(1, 1),
    padding='valid',
    data_format=None,
    dilation_rate=(1, 1),
    depth_multiplier=1,
    activation=None,
    use_bias=True,
    depthwise_initializer='glorot_uniform',
    pointwise_initializer='glorot_uniform',
    bias_initializer='zeros',
    depthwise_regularizer=None,
    pointwise_regularizer=None,
    bias_regularizer=None,
    activity_regularizer=None,
    depthwise_constraint=None,
    pointwise_constraint=None,
    bias_constraint=None,
    **kwargs
)
```







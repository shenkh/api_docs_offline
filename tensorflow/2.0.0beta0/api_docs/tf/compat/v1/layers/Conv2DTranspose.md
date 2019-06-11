<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.layers.Conv2DTranspose" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="scope_name"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.compat.v1.layers.Conv2DTranspose

## Class `Conv2DTranspose`

Transposed 2D convolution layer (sometimes called 2D Deconvolution).

Inherits From: [`Conv2DTranspose`](../../../../tf/keras/layers/Conv2DTranspose.md), [`Layer`](../../../../tf/compat/v1/layers/Layer.md)



Defined in [`python/layers/convolutional.py`](/code/stable/tensorflow/python/layers/convolutional.py).

<!-- Placeholder for "Used in" -->

The need for transposed convolutions generally arises
from the desire to use a transformation going in the opposite direction
of a normal convolution, i.e., from something that has the shape of the
output of some convolution to something that has the shape of its input
while maintaining a connectivity pattern that is compatible with
said convolution.

#### Arguments:


* <b>`filters`</b>: Integer, the dimensionality of the output space (i.e. the number
  of filters in the convolution).
* <b>`kernel_size`</b>: A tuple or list of 2 positive integers specifying the spatial
  dimensions of the filters. Can be a single integer to specify the same
  value for all spatial dimensions.
* <b>`strides`</b>: A tuple or list of 2 positive integers specifying the strides
  of the convolution. Can be a single integer to specify the same value for
  all spatial dimensions.
* <b>`padding`</b>: one of `"valid"` or `"same"` (case-insensitive).
* <b>`data_format`</b>: A string, one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch, height, width, channels)` while `channels_first` corresponds to
  inputs with shape `(batch, channels, height, width)`.
* <b>`activation`</b>: Activation function. Set it to None to maintain a
  linear activation.
* <b>`use_bias`</b>: Boolean, whether the layer uses a bias.
* <b>`kernel_initializer`</b>: An initializer for the convolution kernel.
* <b>`bias_initializer`</b>: An initializer for the bias vector. If None, the default
  initializer will be used.
* <b>`kernel_regularizer`</b>: Optional regularizer for the convolution kernel.
* <b>`bias_regularizer`</b>: Optional regularizer for the bias vector.
* <b>`activity_regularizer`</b>: Optional regularizer function for the output.
* <b>`kernel_constraint`</b>: Optional projection function to be applied to the
    kernel after being updated by an `Optimizer` (e.g. used to implement
    norm constraints or value constraints for layer weights). The function
    must take as input the unprojected variable and must return the
    projected variable (which must have the same shape). Constraints are
    not safe to use when doing asynchronous distributed training.
* <b>`bias_constraint`</b>: Optional projection function to be applied to the
    bias after being updated by an `Optimizer`.
* <b>`trainable`</b>: Boolean, if `True` also add variables to the graph collection
  `GraphKeys.TRAINABLE_VARIABLES` (see <a href="../../../../tf/Variable.md"><code>tf.Variable</code></a>).
* <b>`name`</b>: A string, the name of the layer.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    filters,
    kernel_size,
    strides=(1, 1),
    padding='valid',
    data_format='channels_last',
    activation=None,
    use_bias=True,
    kernel_initializer=None,
    bias_initializer=tf.zeros_initializer(),
    kernel_regularizer=None,
    bias_regularizer=None,
    activity_regularizer=None,
    kernel_constraint=None,
    bias_constraint=None,
    trainable=True,
    name=None,
    **kwargs
)
```






## Properties

<h3 id="graph"><code>graph</code></h3>

DEPRECATED FUNCTION

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Stop using this property because tf.layers layers no longer track their graph.

<h3 id="scope_name"><code>scope_name</code></h3>







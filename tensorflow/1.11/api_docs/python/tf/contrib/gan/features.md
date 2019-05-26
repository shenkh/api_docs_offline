<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.features" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.gan.features



Defined in [`tensorflow/contrib/gan/python/features/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/gan/python/features/__init__.py).

TFGAN features module.

This module includes support for virtual batch normalization, buffer replay,
conditioning, etc.

## Classes

[`class VBN`](../../../tf/contrib/gan/features/VBN.md): A class to perform virtual batch normalization.

## Functions

[`clip_discriminator_weights(...)`](../../../tf/contrib/gan/features/clip_discriminator_weights.md): Modifies an optimizer so it clips weights to a certain value.

[`clip_variables(...)`](../../../tf/contrib/gan/features/clip_variables.md): Modifies an optimizer so it clips weights to a certain value.

[`condition_tensor(...)`](../../../tf/contrib/gan/features/condition_tensor.md): Condition the value of a tensor.

[`condition_tensor_from_onehot(...)`](../../../tf/contrib/gan/features/condition_tensor_from_onehot.md): Condition a tensor based on a one-hot tensor.

[`tensor_pool(...)`](../../../tf/contrib/gan/features/tensor_pool.md): Queue storing input values and returning random previously stored ones.


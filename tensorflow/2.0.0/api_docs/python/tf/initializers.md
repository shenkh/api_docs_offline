<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.initializers" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.initializers

### Aliases:

* Module `tf.initializers`
* Module `tf.keras.initializers`



Defined in [`tensorflow/python/keras/api/_v2/keras/initializers/__init__.py`](/code/stable/tensorflow/python/keras/api/_v2/keras/initializers/__init__.py).

Keras initializer serialization / deserialization.

## Classes

[`class Constant`](../tf/constant_initializer.md): Initializer that generates tensors with constant values.

[`class GlorotNormal`](../tf/initializers/GlorotNormal.md): The Glorot normal initializer, also called Xavier normal initializer.

[`class GlorotUniform`](../tf/initializers/GlorotUniform.md): The Glorot uniform initializer, also called Xavier uniform initializer.

[`class Identity`](../tf/initializers/Identity.md): Initializer that generates the identity matrix.

[`class Initializer`](../tf/initializers/Initializer.md): Initializer base class: all initializers inherit from this class.

[`class Ones`](../tf/ones_initializer.md): Initializer that generates tensors initialized to 1.

[`class Orthogonal`](../tf/initializers/Orthogonal.md): Initializer that generates an orthogonal matrix.

[`class RandomNormal`](../tf/random_normal_initializer.md): Initializer that generates tensors with a normal distribution.

[`class RandomUniform`](../tf/random_uniform_initializer.md): Initializer that generates tensors with a uniform distribution.

[`class TruncatedNormal`](../tf/initializers/TruncatedNormal.md): Initializer that generates a truncated normal distribution.

[`class VarianceScaling`](../tf/initializers/VarianceScaling.md): Initializer capable of adapting its scale to the shape of weights tensors.

[`class Zeros`](../tf/zeros_initializer.md): Initializer that generates tensors initialized to 0.

[`class constant`](../tf/constant_initializer.md): Initializer that generates tensors with constant values.

[`class glorot_normal`](../tf/initializers/GlorotNormal.md): The Glorot normal initializer, also called Xavier normal initializer.

[`class glorot_uniform`](../tf/initializers/GlorotUniform.md): The Glorot uniform initializer, also called Xavier uniform initializer.

[`class identity`](../tf/initializers/Identity.md): Initializer that generates the identity matrix.

[`class ones`](../tf/ones_initializer.md): Initializer that generates tensors initialized to 1.

[`class orthogonal`](../tf/initializers/Orthogonal.md): Initializer that generates an orthogonal matrix.

[`class zeros`](../tf/zeros_initializer.md): Initializer that generates tensors initialized to 0.

## Functions

[`deserialize(...)`](../tf/initializers/deserialize.md): Return an `Initializer` object from its config.

[`get(...)`](../tf/initializers/get.md)

[`he_normal(...)`](../tf/initializers/he_normal.md): He normal initializer.

[`he_uniform(...)`](../tf/initializers/he_uniform.md): He uniform variance scaling initializer.

[`lecun_normal(...)`](../tf/initializers/lecun_normal.md): LeCun normal initializer.

[`lecun_uniform(...)`](../tf/initializers/lecun_uniform.md): LeCun uniform initializer.

[`serialize(...)`](../tf/initializers/serialize.md)


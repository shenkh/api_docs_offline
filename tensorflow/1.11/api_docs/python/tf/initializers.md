<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.initializers" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.initializers



Defined in [`tensorflow/initializers/__init__.py`](https://www.tensorflow.org/code/tensorflow/initializers/__init__.py).

Public API for tf.initializers namespace.

## Classes

[`class constant`](../tf/keras/initializers/Constant.md): Initializer that generates tensors with constant values.

[`class identity`](../tf/keras/initializers/Identity.md): Initializer that generates the identity matrix.

[`class ones`](../tf/keras/initializers/Ones.md): Initializer that generates tensors initialized to 1.

[`class orthogonal`](../tf/keras/initializers/Orthogonal.md): Initializer that generates an orthogonal matrix.

[`class random_normal`](../tf/initializers/random_normal.md): Initializer that generates tensors with a normal distribution.

[`class random_uniform`](../tf/initializers/random_uniform.md): Initializer that generates tensors with a uniform distribution.

[`class truncated_normal`](../tf/initializers/truncated_normal.md): Initializer that generates a truncated normal distribution.

[`class uniform_unit_scaling`](../tf/initializers/uniform_unit_scaling.md): Initializer that generates tensors without scaling variance.

[`class variance_scaling`](../tf/keras/initializers/VarianceScaling.md): Initializer capable of adapting its scale to the shape of weights tensors.

[`class zeros`](../tf/keras/initializers/Zeros.md): Initializer that generates tensors initialized to 0.

## Functions

[`global_variables(...)`](../tf/initializers/global_variables.md): Returns an Op that initializes global variables.

[`glorot_normal(...)`](../tf/glorot_normal_initializer.md): The Glorot normal initializer, also called Xavier normal initializer.

[`glorot_uniform(...)`](../tf/glorot_uniform_initializer.md): The Glorot uniform initializer, also called Xavier uniform initializer.

[`he_normal(...)`](../tf/keras/initializers/he_normal.md): He normal initializer.

[`he_uniform(...)`](../tf/keras/initializers/he_uniform.md): He uniform variance scaling initializer.

[`lecun_normal(...)`](../tf/keras/initializers/lecun_normal.md): LeCun normal initializer.

[`lecun_uniform(...)`](../tf/keras/initializers/lecun_uniform.md): LeCun uniform initializer.

[`local_variables(...)`](../tf/initializers/local_variables.md): Returns an Op that initializes all local variables.

[`variables(...)`](../tf/initializers/variables.md): Returns an Op that initializes a list of variables.


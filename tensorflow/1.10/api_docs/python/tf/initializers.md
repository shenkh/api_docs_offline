<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.initializers" />
</div>

# Module: tf.initializers



Defined in [`tensorflow/initializers/__init__.py`](https://www.tensorflow.org/code/tensorflow/initializers/__init__.py).

Public API for tf.initializers namespace.

## Classes

[`class constant`](../tf/constant_initializer.md): Initializer that generates tensors with constant values.

[`class identity`](../tf/initializers/identity.md): Initializer that generates the identity matrix.

[`class ones`](../tf/ones_initializer.md): Initializer that generates tensors initialized to 1.

[`class orthogonal`](../tf/orthogonal_initializer.md): Initializer that generates an orthogonal matrix.

[`class random_normal`](../tf/random_normal_initializer.md): Initializer that generates tensors with a normal distribution.

[`class random_uniform`](../tf/random_uniform_initializer.md): Initializer that generates tensors with a uniform distribution.

[`class truncated_normal`](../tf/truncated_normal_initializer.md): Initializer that generates a truncated normal distribution.

[`class uniform_unit_scaling`](../tf/uniform_unit_scaling_initializer.md): Initializer that generates tensors without scaling variance.

[`class variance_scaling`](../tf/variance_scaling_initializer.md): Initializer capable of adapting its scale to the shape of weights tensors.

[`class zeros`](../tf/zeros_initializer.md): Initializer that generates tensors initialized to 0.

## Functions

[`global_variables(...)`](../tf/global_variables_initializer.md): Returns an Op that initializes global variables.

[`local_variables(...)`](../tf/local_variables_initializer.md): Returns an Op that initializes all local variables.

[`variables(...)`](../tf/variables_initializer.md): Returns an Op that initializes a list of variables.


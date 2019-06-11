<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.layers.experimental.set_keras_style" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.layers.experimental.set_keras_style

Use Keras-style variable management.

``` python
tf.compat.v1.layers.experimental.set_keras_style()
```



Defined in [`python/layers/base.py`](/code/stable/tensorflow/python/layers/base.py).

<!-- Placeholder for "Used in" -->

All tf.layers and tf RNN cells created after keras style ha been enabled
use Keras-style variable management.  Creating such layers with a
scope= argument is disallowed, and reuse=True is disallowed.

The purpose of this function is to allow users of existing layers to
slowly transition to Keras layers API without breaking existing
functionality.

For more details, see the documentation for `keras_style_scope`.

Note, once keras style has been set, it is set globally for the entire
program and cannot be unset.

#### Example:



```python
set_keras_style()

model_1 = RNNModel(name="model_1")
model_2 = RNNModel(name="model_2")

# model_1 and model_2 are guaranteed to create their own variables.
output_1, next_state_1 = model_1(input, state)
output_2, next_state_2 = model_2(input, state)

assert len(model_1.weights) > 0
assert len(model_2.weights) > 0
assert(model_1.weights != model_2.weights)
```
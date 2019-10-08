<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.experimental.load_from_saved_model" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.experimental.load_from_saved_model

``` python
tf.keras.experimental.load_from_saved_model(
    saved_model_path,
    custom_objects=None
)
```



Defined in [`tensorflow/python/keras/saving/saved_model_experimental.py`](/code/stable/tensorflow/python/keras/saving/saved_model_experimental.py).

Loads a keras Model from a SavedModel created by `export_saved_model()`. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
The experimental save and load functions have been  deprecated. Please switch to <a href="../../../tf/keras/models/load_model.md"><code>tf.keras.models.load_model</code></a>.

This function reinstantiates model state by:
1) loading model topology from json (this will eventually come
   from metagraph).
2) loading model weights from checkpoint.

Example:

```python
import tensorflow as tf

# Create a tf.keras model.
model = tf.keras.Sequential()
model.add(tf.keras.layers.Dense(1, input_shape=[10]))
model.summary()

# Save the tf.keras model in the SavedModel format.
path = '/tmp/simple_keras_model'
tf.keras.experimental.export_saved_model(model, path)

# Load the saved keras model back.
new_model = tf.keras.experimental.load_from_saved_model(path)
new_model.summary()
```

#### Args:

* <b>`saved_model_path`</b>: a string specifying the path to an existing SavedModel.
* <b>`custom_objects`</b>: Optional dictionary mapping names
      (strings) to custom classes or functions to be
      considered during deserialization.


#### Returns:

a keras.Model instance.
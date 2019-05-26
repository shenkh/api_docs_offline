<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.saved_model" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.saved_model



Defined in [`tensorflow/contrib/saved_model/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/saved_model/__init__.py).

SavedModel contrib support.

SavedModel provides a language-neutral format to save machine-learned models
that is recoverable and hermetic. It enables higher-level systems and tools to
produce, consume and transform TensorFlow models.

## Functions

[`get_signature_def_by_key(...)`](../../tf/contrib/saved_model/get_signature_def_by_key.md): Utility function to get a SignatureDef protocol buffer by its key.

[`load_keras_model(...)`](../../tf/contrib/saved_model/load_keras_model.md): Load a keras.Model from SavedModel.

[`save_keras_model(...)`](../../tf/contrib/saved_model/save_keras_model.md): Save a <a href="../../tf/keras/models/Model.md"><code>tf.keras.Model</code></a> into Tensorflow SavedModel format.


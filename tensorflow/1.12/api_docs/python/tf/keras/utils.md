<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.keras.utils



Defined in [`tensorflow/_api/v1/keras/utils/__init__.py`](/code/stable/tensorflow/_api/v1/keras/utils/__init__.py).

Keras utilities.

## Classes

[`class CustomObjectScope`](../../tf/keras/utils/CustomObjectScope.md): Provides a scope that changes to `_GLOBAL_CUSTOM_OBJECTS` cannot escape.

[`class GeneratorEnqueuer`](../../tf/keras/utils/GeneratorEnqueuer.md): Builds a queue out of a data generator.

[`class HDF5Matrix`](../../tf/keras/utils/HDF5Matrix.md): Representation of HDF5 dataset to be used instead of a Numpy array.

[`class OrderedEnqueuer`](../../tf/keras/utils/OrderedEnqueuer.md): Builds a Enqueuer from a Sequence.

[`class Progbar`](../../tf/keras/utils/Progbar.md): Displays a progress bar.

[`class Sequence`](../../tf/keras/utils/Sequence.md): Base object for fitting to a sequence of data, such as a dataset.

[`class SequenceEnqueuer`](../../tf/keras/utils/SequenceEnqueuer.md): Base class to enqueue inputs.

## Functions

[`convert_all_kernels_in_model(...)`](../../tf/keras/utils/convert_all_kernels_in_model.md): Converts all convolution kernels in a model from Theano to TensorFlow.

[`custom_object_scope(...)`](../../tf/keras/utils/custom_object_scope.md): Provides a scope that changes to `_GLOBAL_CUSTOM_OBJECTS` cannot escape.

[`deserialize_keras_object(...)`](../../tf/keras/utils/deserialize_keras_object.md)

[`get_custom_objects(...)`](../../tf/keras/utils/get_custom_objects.md): Retrieves a live reference to the global dictionary of custom objects.

[`get_file(...)`](../../tf/keras/utils/get_file.md): Downloads a file from a URL if it not already in the cache.

[`get_source_inputs(...)`](../../tf/keras/utils/get_source_inputs.md): Returns the list of input tensors necessary to compute `tensor`.

[`multi_gpu_model(...)`](../../tf/keras/utils/multi_gpu_model.md): Replicates a model on different GPUs.

[`normalize(...)`](../../tf/keras/utils/normalize.md): Normalizes a Numpy array.

[`plot_model(...)`](../../tf/keras/utils/plot_model.md): Converts a Keras model to dot format and save to a file.

[`serialize_keras_object(...)`](../../tf/keras/utils/serialize_keras_object.md)

[`to_categorical(...)`](../../tf/keras/utils/to_categorical.md): Converts a class vector (integers) to binary class matrix.


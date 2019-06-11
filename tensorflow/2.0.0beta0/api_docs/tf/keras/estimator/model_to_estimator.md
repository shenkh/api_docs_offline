<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.estimator.model_to_estimator" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.estimator.model_to_estimator

Constructs an `Estimator` instance from given keras model.

### Aliases:

* `tf.compat.v2.keras.estimator.model_to_estimator`
* `tf.keras.estimator.model_to_estimator`

``` python
tf.keras.estimator.model_to_estimator(
    keras_model=None,
    keras_model_path=None,
    custom_objects=None,
    model_dir=None,
    config=None,
    checkpoint_format='checkpoint'
)
```



Defined in [`python/keras/estimator/__init__.py`](/code/stable/tensorflow/python/keras/estimator/__init__.py).

<!-- Placeholder for "Used in" -->

For usage example, please see:
[Creating estimators from Keras
Models](https://tensorflow.org/guide/estimators#model_to_estimator).

#### Args:


* <b>`keras_model`</b>: A compiled Keras model object. This argument is mutually
  exclusive with `keras_model_path`.
* <b>`keras_model_path`</b>: Path to a compiled Keras model saved on disk, in HDF5
  format, which can be generated with the `save()` method of a Keras model.
  This argument is mutually exclusive with `keras_model`.
* <b>`custom_objects`</b>: Dictionary for custom objects.
* <b>`model_dir`</b>: Directory to save `Estimator` model parameters, graph, summary
  files for TensorBoard, etc.
* <b>`config`</b>: `RunConfig` to config `Estimator`.
* <b>`checkpoint_format`</b>: Sets the format of the checkpoint saved by the estimator
  when training. May be `saver` or `checkpoint`, depending on whether to
  save checkpoints from <a href="../../../tf/compat/v1/train/Saver.md"><code>tf.compat.v1.train.Saver</code></a> or <a href="../../../tf/train/Checkpoint.md"><code>tf.train.Checkpoint</code></a>.
  The default is `checkpoint`. Estimators use name-based `tf.train.Saver`
  checkpoints, while Keras models use object-based checkpoints from
  <a href="../../../tf/train/Checkpoint.md"><code>tf.train.Checkpoint</code></a>. Currently, saving object-based checkpoints from
  `model_to_estimator` is only supported by Functional and Sequential
  models.


#### Returns:

An Estimator from given keras model.



#### Raises:


* <b>`ValueError`</b>: if neither keras_model nor keras_model_path was given.
* <b>`ValueError`</b>: if both keras_model and keras_model_path was given.
* <b>`ValueError`</b>: if the keras_model_path is a GCS URI.
* <b>`ValueError`</b>: if keras_model has not been compiled.
* <b>`ValueError`</b>: if an invalid checkpoint_format was given.
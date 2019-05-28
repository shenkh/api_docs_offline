<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.TPUEstimator" />
<meta itemprop="property" content="config"/>
<meta itemprop="property" content="model_dir"/>
<meta itemprop="property" content="model_fn"/>
<meta itemprop="property" content="params"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="eval_dir"/>
<meta itemprop="property" content="evaluate"/>
<meta itemprop="property" content="export_savedmodel"/>
<meta itemprop="property" content="get_variable_names"/>
<meta itemprop="property" content="get_variable_value"/>
<meta itemprop="property" content="latest_checkpoint"/>
<meta itemprop="property" content="predict"/>
<meta itemprop="property" content="train"/>
</div>

# tf.contrib.tpu.TPUEstimator

## Class `TPUEstimator`

Inherits From: [`Estimator`](../../../tf/estimator/Estimator.md)



Defined in [`tensorflow/contrib/tpu/python/tpu/tpu_estimator.py`](https://www.tensorflow.org/code/tensorflow/contrib/tpu/python/tpu/tpu_estimator.py).

Estimator with TPU support.

TPUEstimator handles many of the details of running on TPU devices, such as
replicating inputs and models for each core, and returning to host
periodically to run hooks.

TPUEstimator transforms a global batch size in params to a per-shard batch
size when calling the `input_fn` and `model_fn`. Users should specify
global batch size in constructor, and then get the batch size for each shard
in `input_fn` and `model_fn` by `params['batch_size']`.

- For training, `model_fn` gets per-core batch size; `input_fn` may get
  per-core or per-host batch size depending on `per_host_input_for_training`
  in `TPUConfig` (See docstring for TPUConfig for details).

- For evaluation and prediction, `model_fn` gets per-core batch size and
  `input_fn` get per-host batch size.

Evaluation
==========

`model_fn` should return `TPUEstimatorSpec`, which expects the `eval_metrics`
for TPU evaluation. However, if eval_on_tpu is False, `model_fn` must return
`EstimatorSpec` and the evaluation will execute on CPU or GPU; in this case
the following discussion on TPU evaluation does not apply.

`TPUEstimatorSpec.eval_metrics` is a tuple of `metric_fn` and `tensors`, where
`tensors` could be a list of `Tensor`s or dict of names to `Tensor`s. (See
`TPUEstimatorSpec` for details).  `metric_fn` takes the `tensors` and returns
a dict from metric string name to the result of calling a metric function,
namely a `(metric_tensor, update_op)` tuple.

One can set `use_tpu` to `False` for testing. All training, evaluation, and
predict will be executed on CPU. `input_fn` and `model_fn` will receive
`train_batch_size` or `eval_batch_size` unmodified as `params['batch_size']`.

Current limitations:
--------------------

1. TPU evaluation only works on a single host (one TPU worker).

2. `input_fn` for evaluation should **NOT** raise an end-of-input exception
   (`OutOfRangeError` or `StopIteration`). And all evaluation steps and all
   batches should have the same size.

Example (MNIST):
----------------

```
# The metric Fn which runs on CPU.
def metric_fn(labels, logits):
  predictions = tf.argmax(logits, 1)
  return {
    'accuracy': tf.metrics.precision(
        labels=labels, predictions=predictions),
  }

# Your model Fn which runs on TPU (eval_metrics is list in this example)
def model_fn(features, labels, mode, config, params):
  ...
  logits = ...

  if mode = tf.estimator.ModeKeys.EVAL:
    return tpu_estimator.TPUEstimatorSpec(
        mode=mode,
        loss=loss,
        eval_metrics=(metric_fn, [labels, logits]))

# or specify the eval_metrics tensors as dict.
def model_fn(features, labels, mode, config, params):
  ...
  final_layer_output = ...

  if mode = tf.estimator.ModeKeys.EVAL:
    return tpu_estimator.TPUEstimatorSpec(
        mode=mode,
        loss=loss,
        eval_metrics=(metric_fn, {
            'labels': labels,
            'logits': final_layer_output,
        }))
```

Prediction
==========

Prediction on TPU is an experimental feature to support large batch inference.
It is not designed for latency-critical system. In addition, due to some
usability issues, for prediction with small dataset, CPU `.predict`, i.e.,
creating a new `TPUEstimator` instance with `use_tpu=False`, might be more
convenient.

Note: In contrast to TPU training/evaluation, the `input_fn` for prediction
*should* raise an end-of-input exception (`OutOfRangeError` or
`StopIteration`), which serves as the stopping signal to `TPUEstimator`. To be
precise, the ops created by `input_fn` produce one batch of the data.
The `predict()` API processes one batch at a time. When reaching the end of
the data source, an end-of-input exception should be raised by one of these
operations. The user usually does not need to do this manually. As long as the
dataset is not repeated forever, the <a href="../../../tf/data.md"><code>tf.data</code></a> API will raise an end-of-input
exception automatically after the last batch has been produced.

Note: Estimator.predict returns a Python generator. Please consume all the
data from the generator so that TPUEstimator can shutdown the TPU system
properly for user.

Current limitations:
--------------------
1. TPU prediction only works on a single host (one TPU worker).

2. `input_fn` must return a `Dataset` instance rather than `features`. In
fact, .train() and .evaluate() also support Dataset as return value.

Example (MNIST):
----------------
```
height = 32
width = 32
total_examples = 100

def predict_input_fn(params):
  batch_size = params['batch_size']

  images = tf.random_uniform(
      [total_examples, height, width, 3], minval=-1, maxval=1)

  dataset = tf.data.Dataset.from_tensor_slices(images)
  dataset = dataset.map(lambda images: {'image': images})

  dataset = dataset.batch(batch_size)
  return dataset

def model_fn(features, labels, params, mode):
   # Generate predictions, called 'output', from features['image']

  if mode == tf.estimator.ModeKeys.PREDICT:
    return tf.contrib.tpu.TPUEstimatorSpec(
        mode=mode,
        predictions={
            'predictions': output,
            'is_padding': features['is_padding']
        })

tpu_est = TPUEstimator(
    model_fn=model_fn,
    ...,
    predict_batch_size=16)

# Fully consume the generator so that TPUEstimator can shutdown the TPU
# system.
for item in tpu_est.predict(input_fn=input_fn):
  # Filter out item if the `is_padding` is 1.
  # Process the 'predictions'
```

Exporting
=========

`export_savedmodel` exports 2 metagraphs, one with `tag_constants.SERVING`,
and another with `tag_constants.SERVING` and `tag_constants.TPU`.
At serving time, these tags are used to select metagraph to load.

Before running the graph on TPU, TPU system needs to be initialized. If
TensorFlow Serving model-server is used, this is done automatically. If
not, please call `session.run(tpu.initialize_system())`.

`tpu.outside_compilation` can be used to wrap TPU incompatible ops in
`model_fn`.

Example:
----------------

```
def model_fn(features, labels, mode, config, params):
  ...
  logits = ...
  export_outputs = {
    'logits': export_output_lib.PredictOutput(
      {'logits': logits})
  }

  def host_call(logits):
    class_ids = math_ops.argmax(logits)
    classes = string_ops.as_string(class_ids)
    export_outputs['classes'] =
      export_output_lib.ClassificationOutput(classes=classes)

  tpu.outside_compilation(host_call, logits)

  ...
```

## Properties

<h3 id="config"><code>config</code></h3>



<h3 id="model_dir"><code>model_dir</code></h3>



<h3 id="model_fn"><code>model_fn</code></h3>

Returns the model_fn which is bound to self.params.

#### Returns:

The model_fn with following signature:
  `def model_fn(features, labels, mode, config)`

<h3 id="params"><code>params</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    model_fn=None,
    model_dir=None,
    config=None,
    params=None,
    use_tpu=True,
    train_batch_size=None,
    eval_batch_size=None,
    predict_batch_size=None,
    batch_axis=None,
    eval_on_tpu=True,
    export_to_tpu=True,
    warm_start_from=None
)
```

Constructs an `TPUEstimator` instance.

#### Args:

* <b>`model_fn`</b>: Model function as required by `Estimator`. For training, the
    returned `EstimatorSpec` cannot have hooks as it is not supported in
    `TPUEstimator`. Instead, the user can pass the training hooks as
    an argument to `TPUEstimator.train()`.
* <b>`model_dir`</b>: Directory to save model parameters, graph and etc. This can
    also be used to load checkpoints from the directory into a estimator to
    continue training a previously saved model. If `None`, the model_dir in
    `config` will be used if set. If both are set, they must be same. If
    both are `None`, a temporary directory will be used.
* <b>`config`</b>: An `tpu_config.RunConfig` configuration object. Cannot be `None`.
* <b>`params`</b>: An optional `dict` of hyper parameters that will be passed into
    `input_fn` and `model_fn`.  Keys are names of parameters, values are
    basic python types. There are reserved keys for `TPUEstimator`,
    including 'batch_size'.
* <b>`use_tpu`</b>: A bool indicating whether TPU support is enabled. Currently,
    - TPU training and evaluation respect this bit, but eval_on_tpu can
      override execution of eval. See below.
    - Predict still happens on CPU.
* <b>`train_batch_size`</b>: An int representing the global training batch size.
    TPUEstimator transforms this global batch size to a per-shard batch
    size, as params['batch_size'], when calling `input_fn` and `model_fn`.
    Cannot be `None` if `use_tpu` is `True`.
    Must be divisible by total number of replicas.
* <b>`eval_batch_size`</b>: An int representing evaluation batch size.
    Must be divisible by total number of replicas.
* <b>`predict_batch_size`</b>: An int representing the prediction batch size.
    Must be divisible by total number of replicas.
* <b>`batch_axis`</b>: A python tuple of int values describing how each tensor
    produced by the Estimator `input_fn` should be split across the TPU
    compute shards. For example, if your input_fn produced (images, labels)
    where the images tensor is in `HWCN` format, your shard dimensions would
    be [3, 0], where 3 corresponds to the `N` dimension of your images
    Tensor, and 0 corresponds to the dimension along which to split the
    labels to match up with the corresponding images. If None is supplied,
    and per_host_input_for_training is True, batches will be sharded based
    on the major dimension. If tpu_config.per_host_input_for_training is
    False or `PER_HOST_V2`, batch_axis is ignored.
* <b>`eval_on_tpu`</b>: If False, evaluation runs on CPU or GPU. In this case, the
    model_fn must return `EstimatorSpec` when called with `mode` as `EVAL`.
* <b>`export_to_tpu`</b>: If True, `export_savedmodel()` exports a metagraph for
    serving on TPU besides the one on CPU.
* <b>`warm_start_from`</b>: Optional string filepath to a checkpoint or SavedModel to
                   warm-start from, or a <a href="../../../tf/estimator/WarmStartSettings.md"><code>tf.estimator.WarmStartSettings</code></a>
                   object to fully configure warm-starting.  If the string
                   filepath is provided instead of a `WarmStartSettings`,
                   then all variables are warm-started, and it is assumed
                   that vocabularies and Tensor names are unchanged.


#### Raises:

* <b>`ValueError`</b>: `params` has reserved keys already.

<h3 id="eval_dir"><code>eval_dir</code></h3>

``` python
eval_dir(name=None)
```

Shows directory name where evaluation metrics are dumped.

#### Args:

* <b>`name`</b>: Name of the evaluation if user needs to run multiple evaluations on
    different data sets, such as on training data vs test data. Metrics for
    different evaluations are saved in separate folders, and appear
    separately in tensorboard.


#### Returns:

A string which is the path of directory contains evaluation metrics.

<h3 id="evaluate"><code>evaluate</code></h3>

``` python
evaluate(
    input_fn,
    steps=None,
    hooks=None,
    checkpoint_path=None,
    name=None
)
```

Evaluates the model given evaluation data input_fn.

For each step, calls `input_fn`, which returns one batch of data.
Evaluates until:
- `steps` batches are processed, or
- `input_fn` raises an end-of-input exception (`OutOfRangeError` or
`StopIteration`).

#### Args:

* <b>`input_fn`</b>: A function that constructs the input data for evaluation.
    See <a href="../../../../../guide/premade_estimators.md#create_input_functions">Premade Estimators</a> for more
    information. The function should construct and return one of
    the following:

      * A 'tf.data.Dataset' object: Outputs of `Dataset` object must be a
        tuple (features, labels) with same constraints as below.
      * A tuple (features, labels): Where `features` is a `Tensor` or a
        dictionary of string feature name to `Tensor` and `labels` is a
        `Tensor` or a dictionary of string label name to `Tensor`. Both
        `features` and `labels` are consumed by `model_fn`. They should
        satisfy the expectation of `model_fn` from inputs.

* <b>`steps`</b>: Number of steps for which to evaluate model. If `None`, evaluates
    until `input_fn` raises an end-of-input exception.
* <b>`hooks`</b>: List of `SessionRunHook` subclass instances. Used for callbacks
    inside the evaluation call.
* <b>`checkpoint_path`</b>: Path of a specific checkpoint to evaluate. If `None`, the
    latest checkpoint in `model_dir` is used.  If there are no checkpoints
    in `model_dir`, evaluation is run with newly initialized `Variables`
    instead of restored from checkpoint.
* <b>`name`</b>: Name of the evaluation if user needs to run multiple evaluations on
    different data sets, such as on training data vs test data. Metrics for
    different evaluations are saved in separate folders, and appear
    separately in tensorboard.


#### Returns:

A dict containing the evaluation metrics specified in `model_fn` keyed by
name, as well as an entry `global_step` which contains the value of the
global step for which this evaluation was performed.


#### Raises:

* <b>`ValueError`</b>: If `steps <= 0`.
* <b>`ValueError`</b>: If no model has been trained, namely `model_dir`, or the
    given `checkpoint_path` is empty.

<h3 id="export_savedmodel"><code>export_savedmodel</code></h3>

``` python
export_savedmodel(
    export_dir_base,
    serving_input_receiver_fn,
    assets_extra=None,
    as_text=False,
    checkpoint_path=None,
    strip_default_attrs=False
)
```

Exports inference graph as a SavedModel into given dir.

For a detailed guide, see
<a href="../../../../../guide/saved_model.md#using_savedmodel_with_estimators">Using SavedModel with Estimators</a>.

This method builds a new graph by first calling the
serving_input_receiver_fn to obtain feature `Tensor`s, and then calling
this `Estimator`'s model_fn to generate the model graph based on those
features. It restores the given checkpoint (or, lacking that, the most
recent checkpoint) into this graph in a fresh session.  Finally it creates
a timestamped export directory below the given export_dir_base, and writes
a `SavedModel` into it containing a single `MetaGraphDef` saved from this
session.

The exported `MetaGraphDef` will provide one `SignatureDef` for each
element of the export_outputs dict returned from the model_fn, named using
the same keys.  One of these keys is always
signature_constants.DEFAULT_SERVING_SIGNATURE_DEF_KEY, indicating which
signature will be served when a serving request does not specify one.
For each signature, the outputs are provided by the corresponding
`ExportOutput`s, and the inputs are always the input receivers provided by
the serving_input_receiver_fn.

Extra assets may be written into the SavedModel via the assets_extra
argument.  This should be a dict, where each key gives a destination path
(including the filename) relative to the assets.extra directory.  The
corresponding value gives the full path of the source file to be copied.
For example, the simple case of copying a single file without renaming it
is specified as `{'my_asset_file.txt': '/path/to/my_asset_file.txt'}`.

#### Args:

* <b>`export_dir_base`</b>: A string containing a directory in which to create
    timestamped subdirectories containing exported SavedModels.
* <b>`serving_input_receiver_fn`</b>: A function that takes no argument and
    returns a `ServingInputReceiver` or `TensorServingInputReceiver`.
* <b>`assets_extra`</b>: A dict specifying how to populate the assets.extra directory
    within the exported SavedModel, or `None` if no extra assets are needed.
* <b>`as_text`</b>: whether to write the SavedModel proto in text format.
* <b>`checkpoint_path`</b>: The checkpoint path to export.  If `None` (the default),
    the most recent checkpoint found within the model directory is chosen.
* <b>`strip_default_attrs`</b>: Boolean. If `True`, default-valued attributes will be
    removed from the NodeDefs. For a detailed guide, see
    [Stripping Default-Valued Attributes](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/saved_model/README.md#stripping-default-valued-attributes).


#### Returns:

The string path to the exported directory.


#### Raises:

* <b>`ValueError`</b>: if no serving_input_receiver_fn is provided, no export_outputs
      are provided, or no checkpoint can be found.

<h3 id="get_variable_names"><code>get_variable_names</code></h3>

``` python
get_variable_names()
```

Returns list of all variable names in this model.

#### Returns:

List of names.


#### Raises:

* <b>`ValueError`</b>: If the Estimator has not produced a checkpoint yet.

<h3 id="get_variable_value"><code>get_variable_value</code></h3>

``` python
get_variable_value(name)
```

Returns value of the variable given by name.

#### Args:

* <b>`name`</b>: string or a list of string, name of the tensor.


#### Returns:

Numpy array - value of the tensor.


#### Raises:

* <b>`ValueError`</b>: If the Estimator has not produced a checkpoint yet.

<h3 id="latest_checkpoint"><code>latest_checkpoint</code></h3>

``` python
latest_checkpoint()
```

Finds the filename of latest saved checkpoint file in `model_dir`.

#### Returns:

The full path to the latest checkpoint or `None` if no checkpoint was
found.

<h3 id="predict"><code>predict</code></h3>

``` python
predict(
    input_fn,
    predict_keys=None,
    hooks=None,
    checkpoint_path=None,
    yield_single_examples=True
)
```

Yields predictions for given features.

#### Args:

* <b>`input_fn`</b>: A function that constructs the features. Prediction continues
    until `input_fn` raises an end-of-input exception (`OutOfRangeError` or
    `StopIteration`).
    See <a href="../../../../../guide/premade_estimators.md#create_input_functions">Premade Estimators</a> for more
    information. The function should construct and return one of
    the following:

      * A 'tf.data.Dataset' object: Outputs of `Dataset` object must have
        same constraints as below.
      * features: A `Tensor` or a dictionary of string feature name to
        `Tensor`. features are consumed by `model_fn`. They should satisfy
        the expectation of `model_fn` from inputs.
      * A tuple, in which case the first item is extracted as features.

* <b>`predict_keys`</b>: list of `str`, name of the keys to predict. It is used if
    the `EstimatorSpec.predictions` is a `dict`. If `predict_keys` is used
    then rest of the predictions will be filtered from the dictionary. If
    `None`, returns all.
* <b>`hooks`</b>: List of `SessionRunHook` subclass instances. Used for callbacks
    inside the prediction call.
* <b>`checkpoint_path`</b>: Path of a specific checkpoint to predict. If `None`, the
    latest checkpoint in `model_dir` is used.  If there are no checkpoints
    in `model_dir`, prediction is run with newly initialized `Variables`
    instead of restored from checkpoint.
* <b>`yield_single_examples`</b>: If False, yield the whole batch as returned by the
    `model_fn` instead of decomposing the batch into individual elements.
    This is useful if `model_fn` returns some tensors whose first dimension
    is not equal to the batch size.


#### Yields:

Evaluated values of `predictions` tensors.


#### Raises:

* <b>`ValueError`</b>: Could not find a trained model in `model_dir`.
* <b>`ValueError`</b>: If batch length of predictions is not the same and
    `yield_single_examples` is True.
* <b>`ValueError`</b>: If there is a conflict between `predict_keys` and
    `predictions`. For example if `predict_keys` is not `None` but
    `EstimatorSpec.predictions` is not a `dict`.

<h3 id="train"><code>train</code></h3>

``` python
train(
    input_fn,
    hooks=None,
    steps=None,
    max_steps=None,
    saving_listeners=None
)
```

Trains a model given training data input_fn.

#### Args:

* <b>`input_fn`</b>: A function that provides input data for training as minibatches.
    See <a href="../../../../../guide/premade_estimators.md#create_input_functions">Premade Estimators</a> for more
    information. The function should construct and return one of
    the following:

      * A 'tf.data.Dataset' object: Outputs of `Dataset` object must be a
        tuple (features, labels) with same constraints as below.
      * A tuple (features, labels): Where `features` is a `Tensor` or a
        dictionary of string feature name to `Tensor` and `labels` is a
        `Tensor` or a dictionary of string label name to `Tensor`. Both
        `features` and `labels` are consumed by `model_fn`. They should
        satisfy the expectation of `model_fn` from inputs.

* <b>`hooks`</b>: List of `SessionRunHook` subclass instances. Used for callbacks
    inside the training loop.
* <b>`steps`</b>: Number of steps for which to train model. If `None`, train forever
    or train until input_fn generates the `OutOfRange` error or
    `StopIteration` exception. 'steps' works incrementally. If you call two
    times train(steps=10) then training occurs in total 20 steps. If
    `OutOfRange` or `StopIteration` occurs in the middle, training stops
    before 20 steps. If you don't want to have incremental behavior please
    set `max_steps` instead. If set, `max_steps` must be `None`.
* <b>`max_steps`</b>: Number of total steps for which to train model. If `None`,
    train forever or train until input_fn generates the `OutOfRange` error
    or `StopIteration` exception. If set, `steps` must be `None`. If
    `OutOfRange` or `StopIteration` occurs in the middle, training stops
    before `max_steps` steps.
    Two calls to `train(steps=100)` means 200 training
    iterations. On the other hand, two calls to `train(max_steps=100)` means
    that the second call will not do any iteration since first call did
    all 100 steps.
* <b>`saving_listeners`</b>: list of `CheckpointSaverListener` objects. Used for
    callbacks that run immediately before or after checkpoint savings.


#### Returns:

`self`, for chaining.


#### Raises:

* <b>`ValueError`</b>: If both `steps` and `max_steps` are not `None`.
* <b>`ValueError`</b>: If either `steps` or `max_steps` is <= 0.




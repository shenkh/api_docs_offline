<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.experimental.RNNClassifier" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="config"/>
<meta itemprop="property" content="model_dir"/>
<meta itemprop="property" content="model_fn"/>
<meta itemprop="property" content="params"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="eval_dir"/>
<meta itemprop="property" content="evaluate"/>
<meta itemprop="property" content="experimental_export_all_saved_models"/>
<meta itemprop="property" content="export_saved_model"/>
<meta itemprop="property" content="export_savedmodel"/>
<meta itemprop="property" content="get_variable_names"/>
<meta itemprop="property" content="get_variable_value"/>
<meta itemprop="property" content="latest_checkpoint"/>
<meta itemprop="property" content="predict"/>
<meta itemprop="property" content="train"/>
</div>

# tf.estimator.experimental.RNNClassifier

## Class `RNNClassifier`

Inherits From: [`RNNEstimator`](../../../tf/estimator/experimental/RNNEstimator.md)

A classifier for TensorFlow RNN models.

Trains a recurrent neural network model to classify instances into one of
multiple classes.

Example:

```python
token_sequence = sequence_categorical_column_with_hash_bucket(...)
token_emb = embedding_column(categorical_column=token_sequence, ...)

estimator = RNNClassifier(
    sequence_feature_columns=[token_emb],
    units=[32, 16], cell_type='lstm')

# Input builders
def input_fn_train: # returns x, y
  pass
estimator.train(input_fn=input_fn_train, steps=100)

def input_fn_eval: # returns x, y
  pass
metrics = estimator.evaluate(input_fn=input_fn_eval, steps=10)
def input_fn_predict: # returns x, None
  pass
predictions = estimator.predict(input_fn=input_fn_predict)
```

Input of `train` and `evaluate` should have following features,
otherwise there will be a `KeyError`:

* if `weight_column` is not `None`, a feature with
  `key=weight_column` whose value is a `Tensor`.
* for each `column` in `sequence_feature_columns`:
  - a feature with `key=column.name` whose `value` is a `SparseTensor`.
* for each `column` in `context_feature_columns`:
  - if `column` is a `CategoricalColumn`, a feature with `key=column.name`
    whose `value` is a `SparseTensor`.
  - if `column` is a `WeightedCategoricalColumn`, two features: the first
    with `key` the id column name, the second with `key` the weight column
    name. Both features' `value` must be a `SparseTensor`.
  - if `column` is a `DenseColumn`, a feature with `key=column.name`
    whose `value` is a `Tensor`.

Loss is calculated by using softmax cross entropy.



#### Eager Compatibility
Estimators are not compatible with eager execution.



<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    sequence_feature_columns,
    context_feature_columns=None,
    units=None,
    cell_type=USE_DEFAULT,
    rnn_cell_fn=None,
    return_sequences=False,
    model_dir=None,
    n_classes=2,
    weight_column=None,
    label_vocabulary=None,
    optimizer='Adagrad',
    loss_reduction=losses_utils.ReductionV2.SUM_OVER_BATCH_SIZE,
    sequence_mask='sequence_mask',
    config=None
)
```

Initializes a `RNNClassifier` instance.

#### Args:

* <b>`sequence_feature_columns`</b>: An iterable containing the `FeatureColumn`s
    that represent sequential input. All items in the set should either be
    sequence columns (e.g. `sequence_numeric_column`) or constructed from
    one (e.g. `embedding_column` with `sequence_categorical_column_*` as
    input).
* <b>`context_feature_columns`</b>: An iterable containing the `FeatureColumn`s
    for contextual input. The data represented by these columns will be
    replicated and given to the RNN at each timestep. These columns must be
    instances of classes derived from `DenseColumn` such as
    `numeric_column`, not the sequential variants.
* <b>`units`</b>: Iterable of integer number of hidden units per RNN layer. If
    set, `cell_type` must also be specified and `rnn_cell_fn` must be
    `None`.
* <b>`cell_type`</b>: A class producing a RNN cell or a string specifying the cell
    type. Supported strings are: `'simple_rnn'`, `'lstm'`, and `'gru'`. If
    set, `units` must also be specified and `rnn_cell_fn` must be `None`.
* <b>`rnn_cell_fn`</b>: A function that returns a RNN cell instance that will be used
    to construct the RNN. If set, `units` and `cell_type` cannot be set.
    This is for advanced users who need additional customization beyond
    `units` and `cell_type`. Note that <a href="../../../tf/keras/layers/StackedRNNCells.md"><code>tf.keras.layers.StackedRNNCells</code></a> is
    needed for stacked RNNs.
* <b>`return_sequences`</b>: A boolean indicating whether to return the last output
    in the output sequence, or the full sequence. Note that if True,
    `weight_column` must be None or a string.
* <b>`model_dir`</b>: Directory to save model parameters, graph and etc. This can
    also be used to load checkpoints from the directory into a estimator to
    continue training a previously saved model.
* <b>`n_classes`</b>: Number of label classes. Defaults to 2, namely binary
    classification. Must be > 1.
* <b>`weight_column`</b>: A string or a `NumericColumn` created by
    <a href="../../../tf/feature_column/numeric_column.md"><code>tf.feature_column.numeric_column</code></a> defining feature column representing
    weights. It is used to down weight or boost examples during training. It
    will be multiplied by the loss of the example. If it is a string, it is
    used as a key to fetch weight tensor from the `features`. If it is a
    `NumericColumn`, raw tensor is fetched by key `weight_column.key`, then
    weight_column.normalizer_fn is applied on it to get weight tensor.
* <b>`label_vocabulary`</b>: A list of strings represents possible label values. If
    given, labels must be string type and have any value in
    `label_vocabulary`. If it is not given, that means labels are
    already encoded as integer or float within [0, 1] for `n_classes=2` and
    encoded as integer values in {0, 1,..., n_classes-1} for `n_classes`>2 .
    Also there will be errors if vocabulary is not provided and labels are
    string.
* <b>`optimizer`</b>: An instance of `tf.Optimizer` or string specifying optimizer
    type. Defaults to Adagrad optimizer.
* <b>`loss_reduction`</b>: One of <a href="../../../tf/losses/Reduction.md"><code>tf.losses.Reduction</code></a> except `NONE`. Describes how
    to reduce training loss over batch. Defaults to `SUM_OVER_BATCH_SIZE`.
* <b>`sequence_mask`</b>: A string with the name of the sequence mask tensor. If
    `sequence_mask` is in the features dictionary, the provided tensor is
    used, otherwise the sequence mask is computed from the length of
    sequential features. The sequence mask is used in evaluation and
    training mode to aggregate loss and metrics computation while excluding
    padding steps. It is also added to the predictions dictionary in
    prediction mode to indicate which steps are padding.
* <b>`config`</b>: `RunConfig` object to configure the runtime settings.

Note that a RNN cell has:
  - a `call` method.
  - a `state_size` attribute.
  - a `output_size` attribute.
  - a `get_initial_state` method.
See the documentation on <a href="../../../tf/keras/layers/RNN.md"><code>tf.keras.layers.RNN</code></a> for more details.


#### Raises:

* <b>`ValueError`</b>: If `units`, `cell_type`, and `rnn_cell_fn` are not
    compatible.



## Properties

<h3 id="config"><code>config</code></h3>



<h3 id="model_dir"><code>model_dir</code></h3>



<h3 id="model_fn"><code>model_fn</code></h3>

Returns the `model_fn` which is bound to `self.params`.

#### Returns:

The `model_fn` with following signature:
  `def model_fn(features, labels, mode, config)`

<h3 id="params"><code>params</code></h3>





## Methods

<h3 id="eval_dir"><code>eval_dir</code></h3>

``` python
eval_dir(name=None)
```

Shows the directory name where evaluation metrics are dumped.

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

Evaluates the model given evaluation data `input_fn`.

For each step, calls `input_fn`, which returns one batch of data.
Evaluates until:
- `steps` batches are processed, or
- `input_fn` raises an end-of-input exception (<a href="../../../tf/errors/OutOfRangeError.md"><code>tf.errors.OutOfRangeError</code></a>
or
`StopIteration`).

#### Args:

* <b>`input_fn`</b>: A function that constructs the input data for evaluation. See
    [Premade Estimators](
    https://tensorflow.org/guide/premade_estimators#create_input_functions)
    for more information. The
    function should construct and return one of the following:  * A
    <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object: Outputs of `Dataset` object must be a tuple
    `(features, labels)` with same constraints as below. * A tuple
    `(features, labels)`: Where `features` is a <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> or a dictionary
    of string feature name to `Tensor` and `labels` is a `Tensor` or a
    dictionary of string label name to `Tensor`. Both `features` and
    `labels` are consumed by `model_fn`. They should satisfy the expectation
    of `model_fn` from inputs.
* <b>`steps`</b>: Number of steps for which to evaluate model. If `None`, evaluates
    until `input_fn` raises an end-of-input exception.
* <b>`hooks`</b>: List of `tf.train.SessionRunHook` subclass instances. Used for
    callbacks inside the evaluation call.
* <b>`checkpoint_path`</b>: Path of a specific checkpoint to evaluate. If `None`, the
    latest checkpoint in `model_dir` is used.  If there are no checkpoints
    in `model_dir`, evaluation is run with newly initialized `Variables`
    instead of ones restored from checkpoint.
* <b>`name`</b>: Name of the evaluation if user needs to run multiple evaluations on
    different data sets, such as on training data vs test data. Metrics for
    different evaluations are saved in separate folders, and appear
    separately in tensorboard.


#### Returns:

A dict containing the evaluation metrics specified in `model_fn` keyed by
name, as well as an entry `global_step` which contains the value of the
global step for which this evaluation was performed. For canned
estimators, the dict contains the `loss` (mean loss per mini-batch) and
the `average_loss` (mean loss per sample). Canned classifiers also return
the `accuracy`. Canned regressors also return the `label/mean` and the
`prediction/mean`.


#### Raises:

* <b>`ValueError`</b>: If `steps <= 0`.

<h3 id="experimental_export_all_saved_models"><code>experimental_export_all_saved_models</code></h3>

``` python
experimental_export_all_saved_models(
    export_dir_base,
    input_receiver_fn_map,
    assets_extra=None,
    as_text=False,
    checkpoint_path=None
)
```

Exports a `SavedModel` with `tf.MetaGraphDefs` for each requested mode.

For each mode passed in via the `input_receiver_fn_map`,
this method builds a new graph by calling the `input_receiver_fn` to obtain
feature and label `Tensor`s. Next, this method calls the `Estimator`'s
`model_fn` in the passed mode to generate the model graph based on
those features and labels, and restores the given checkpoint
(or, lacking that, the most recent checkpoint) into the graph.
Only one of the modes is used for saving variables to the `SavedModel`
(order of preference: <a href="../../../tf/estimator/ModeKeys.md#TRAIN"><code>tf.estimator.ModeKeys.TRAIN</code></a>,
<a href="../../../tf/estimator/ModeKeys.md#EVAL"><code>tf.estimator.ModeKeys.EVAL</code></a>, then
<a href="../../../tf/estimator/ModeKeys.md#PREDICT"><code>tf.estimator.ModeKeys.PREDICT</code></a>), such that up to three
`tf.MetaGraphDefs` are saved with a single set of variables in a single
`SavedModel` directory.

For the variables and `tf.MetaGraphDefs`, a timestamped export directory
below
`export_dir_base`, and writes a `SavedModel` into it containing
the `tf.MetaGraphDef` for the given mode and its associated signatures.

For prediction, the exported `MetaGraphDef` will provide one `SignatureDef`
for each element of the `export_outputs` dict returned from the `model_fn`,
named using the same keys.  One of these keys is always
`tf.saved_model.signature_constants.DEFAULT_SERVING_SIGNATURE_DEF_KEY`,
indicating which
signature will be served when a serving request does not specify one.
For each signature, the outputs are provided by the corresponding
<a href="../../../tf/estimator/export/ExportOutput.md"><code>tf.estimator.export.ExportOutput</code></a>s, and the inputs are always the input
receivers provided by
the `serving_input_receiver_fn`.

For training and evaluation, the `train_op` is stored in an extra
collection,
and loss, metrics, and predictions are included in a `SignatureDef` for the
mode in question.

Extra assets may be written into the `SavedModel` via the `assets_extra`
argument.  This should be a dict, where each key gives a destination path
(including the filename) relative to the assets.extra directory.  The
corresponding value gives the full path of the source file to be copied.
For example, the simple case of copying a single file without renaming it
is specified as `{'my_asset_file.txt': '/path/to/my_asset_file.txt'}`.

#### Args:

* <b>`export_dir_base`</b>: A string containing a directory in which to create
    timestamped subdirectories containing exported `SavedModel`s.
* <b>`input_receiver_fn_map`</b>: dict of <a href="../../../tf/estimator/ModeKeys.md"><code>tf.estimator.ModeKeys</code></a> to
    `input_receiver_fn` mappings, where the `input_receiver_fn` is a
    function that takes no arguments and returns the appropriate subclass of
    `InputReceiver`.
* <b>`assets_extra`</b>: A dict specifying how to populate the assets.extra directory
    within the exported `SavedModel`, or `None` if no extra assets are
    needed.
* <b>`as_text`</b>: whether to write the `SavedModel` proto in text format.
* <b>`checkpoint_path`</b>: The checkpoint path to export.  If `None` (the default),
    the most recent checkpoint found within the model directory is chosen.


#### Returns:

The string path to the exported directory.


#### Raises:

* <b>`ValueError`</b>: if any `input_receiver_fn` is `None`, no `export_outputs`
    are provided, or no checkpoint can be found.

<h3 id="export_saved_model"><code>export_saved_model</code></h3>

``` python
export_saved_model(
    export_dir_base,
    serving_input_receiver_fn,
    assets_extra=None,
    as_text=False,
    checkpoint_path=None,
    experimental_mode=ModeKeys.PREDICT
)
```

Exports inference graph as a `SavedModel` into the given dir.

For a detailed guide, see
[Using SavedModel with Estimators](https://tensorflow.org/guide/saved_model#using_savedmodel_with_estimators).

This method builds a new graph by first calling the
`serving_input_receiver_fn` to obtain feature `Tensor`s, and then calling
this `Estimator`'s `model_fn` to generate the model graph based on those
features. It restores the given checkpoint (or, lacking that, the most
recent checkpoint) into this graph in a fresh session.  Finally it creates
a timestamped export directory below the given `export_dir_base`, and writes
a `SavedModel` into it containing a single `tf.MetaGraphDef` saved from this
session.

The exported `MetaGraphDef` will provide one `SignatureDef` for each
element of the `export_outputs` dict returned from the `model_fn`, named
using
the same keys.  One of these keys is always
`tf.saved_model.signature_constants.DEFAULT_SERVING_SIGNATURE_DEF_KEY`,
indicating which
signature will be served when a serving request does not specify one.
For each signature, the outputs are provided by the corresponding
<a href="../../../tf/estimator/export/ExportOutput.md"><code>tf.estimator.export.ExportOutput</code></a>s, and the inputs are always the input
receivers provided by
the `serving_input_receiver_fn`.

Extra assets may be written into the `SavedModel` via the `assets_extra`
argument.  This should be a dict, where each key gives a destination path
(including the filename) relative to the assets.extra directory.  The
corresponding value gives the full path of the source file to be copied.
For example, the simple case of copying a single file without renaming it
is specified as `{'my_asset_file.txt': '/path/to/my_asset_file.txt'}`.

The experimental_mode parameter can be used to export a single
train/eval/predict graph as a `SavedModel`.
See `experimental_export_all_saved_models` for full docs.

#### Args:

* <b>`export_dir_base`</b>: A string containing a directory in which to create
    timestamped subdirectories containing exported `SavedModel`s.
* <b>`serving_input_receiver_fn`</b>: A function that takes no argument and returns a
    <a href="../../../tf/estimator/export/ServingInputReceiver.md"><code>tf.estimator.export.ServingInputReceiver</code></a> or
    <a href="../../../tf/estimator/export/TensorServingInputReceiver.md"><code>tf.estimator.export.TensorServingInputReceiver</code></a>.
* <b>`assets_extra`</b>: A dict specifying how to populate the assets.extra directory
    within the exported `SavedModel`, or `None` if no extra assets are
    needed.
* <b>`as_text`</b>: whether to write the `SavedModel` proto in text format.
* <b>`checkpoint_path`</b>: The checkpoint path to export.  If `None` (the default),
    the most recent checkpoint found within the model directory is chosen.
* <b>`experimental_mode`</b>: <a href="../../../tf/estimator/ModeKeys.md"><code>tf.estimator.ModeKeys</code></a> value indicating with mode
    will be exported. Note that this feature is experimental.


#### Returns:

The string path to the exported directory.


#### Raises:

* <b>`ValueError`</b>: if no `serving_input_receiver_fn` is provided, no
  `export_outputs` are provided, or no checkpoint can be found.

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

Exports inference graph as a `SavedModel` into the given dir. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
This function has been renamed, use `export_saved_model` instead.

For a detailed guide, see
[Using SavedModel with Estimators](https://tensorflow.org/guide/saved_model#using_savedmodel_with_estimators).

This method builds a new graph by first calling the
`serving_input_receiver_fn` to obtain feature `Tensor`s, and then calling
this `Estimator`'s `model_fn` to generate the model graph based on those
features. It restores the given checkpoint (or, lacking that, the most
recent checkpoint) into this graph in a fresh session.  Finally it creates
a timestamped export directory below the given `export_dir_base`, and writes
a `SavedModel` into it containing a single `tf.MetaGraphDef` saved from this
session.

The exported `MetaGraphDef` will provide one `SignatureDef` for each
element of the `export_outputs` dict returned from the `model_fn`, named
using
the same keys.  One of these keys is always
`tf.saved_model.signature_constants.DEFAULT_SERVING_SIGNATURE_DEF_KEY`,
indicating which
signature will be served when a serving request does not specify one.
For each signature, the outputs are provided by the corresponding
<a href="../../../tf/estimator/export/ExportOutput.md"><code>tf.estimator.export.ExportOutput</code></a>s, and the inputs are always the input
receivers provided by
the `serving_input_receiver_fn`.

Extra assets may be written into the `SavedModel` via the `assets_extra`
argument.  This should be a dict, where each key gives a destination path
(including the filename) relative to the assets.extra directory.  The
corresponding value gives the full path of the source file to be copied.
For example, the simple case of copying a single file without renaming it
is specified as `{'my_asset_file.txt': '/path/to/my_asset_file.txt'}`.

#### Args:

* <b>`export_dir_base`</b>: A string containing a directory in which to create
    timestamped subdirectories containing exported `SavedModel`s.
* <b>`serving_input_receiver_fn`</b>: A function that takes no argument and returns a
    <a href="../../../tf/estimator/export/ServingInputReceiver.md"><code>tf.estimator.export.ServingInputReceiver</code></a> or
    <a href="../../../tf/estimator/export/TensorServingInputReceiver.md"><code>tf.estimator.export.TensorServingInputReceiver</code></a>.
* <b>`assets_extra`</b>: A dict specifying how to populate the assets.extra directory
    within the exported `SavedModel`, or `None` if no extra assets are
    needed.
* <b>`as_text`</b>: whether to write the `SavedModel` proto in text format.
* <b>`checkpoint_path`</b>: The checkpoint path to export.  If `None` (the default),
    the most recent checkpoint found within the model directory is chosen.
* <b>`strip_default_attrs`</b>: Boolean. If `True`, default-valued attributes will be
    removed from the `NodeDef`s. For a detailed guide, see [Stripping
    Default-Valued Attributes](
    https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/saved_model/README.md#stripping-default-valued-attributes).


#### Returns:

The string path to the exported directory.


#### Raises:

* <b>`ValueError`</b>: if no `serving_input_receiver_fn` is provided, no
  `export_outputs` are provided, or no checkpoint can be found.

<h3 id="get_variable_names"><code>get_variable_names</code></h3>

``` python
get_variable_names()
```

Returns list of all variable names in this model.

#### Returns:

List of names.


#### Raises:

* <b>`ValueError`</b>: If the `Estimator` has not produced a checkpoint yet.

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

* <b>`ValueError`</b>: If the `Estimator` has not produced a checkpoint yet.

<h3 id="latest_checkpoint"><code>latest_checkpoint</code></h3>

``` python
latest_checkpoint()
```

Finds the filename of the latest saved checkpoint file in `model_dir`.

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

Please note that interleaving two predict outputs does not work. See:
[issue/20506](
https://github.com/tensorflow/tensorflow/issues/20506#issuecomment-422208517)

#### Args:

* <b>`input_fn`</b>: A function that constructs the features. Prediction continues
    until `input_fn` raises an end-of-input exception
    (<a href="../../../tf/errors/OutOfRangeError.md"><code>tf.errors.OutOfRangeError</code></a> or `StopIteration`).
    See [Premade Estimators](
    https://tensorflow.org/guide/premade_estimators#create_input_functions)
    for more information. The function should construct and return one of
    the following:

      * A <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object: Outputs of `Dataset` object must have
        same constraints as below.
      * features: A <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> or a dictionary of string feature name to
        `Tensor`. features are consumed by `model_fn`. They should satisfy
        the expectation of `model_fn` from inputs.
      * A tuple, in which case the first item is extracted as features.

* <b>`predict_keys`</b>: list of `str`, name of the keys to predict. It is used if
    the <a href="../../../tf/estimator/EstimatorSpec.md#predictions"><code>tf.estimator.EstimatorSpec.predictions</code></a> is a `dict`. If
    `predict_keys` is used then rest of the predictions will be filtered
    from the dictionary. If `None`, returns all.
* <b>`hooks`</b>: List of `tf.train.SessionRunHook` subclass instances. Used for
    callbacks inside the prediction call.
* <b>`checkpoint_path`</b>: Path of a specific checkpoint to predict. If `None`, the
    latest checkpoint in `model_dir` is used.  If there are no checkpoints
    in `model_dir`, prediction is run with newly initialized `Variables`
    instead of ones restored from checkpoint.
* <b>`yield_single_examples`</b>: If `False`, yields the whole batch as returned by
    the `model_fn` instead of decomposing the batch into individual
    elements. This is useful if `model_fn` returns some tensors whose first
    dimension is not equal to the batch size.


#### Yields:

Evaluated values of `predictions` tensors.


#### Raises:

* <b>`ValueError`</b>: If batch length of predictions is not the same and
    `yield_single_examples` is `True`.
* <b>`ValueError`</b>: If there is a conflict between `predict_keys` and
    `predictions`. For example if `predict_keys` is not `None` but
    <a href="../../../tf/estimator/EstimatorSpec.md#predictions"><code>tf.estimator.EstimatorSpec.predictions</code></a> is not a `dict`.

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

Trains a model given training data `input_fn`.

#### Args:

* <b>`input_fn`</b>: A function that provides input data for training as minibatches.
    See [Premade Estimators](
    https://tensorflow.org/guide/premade_estimators#create_input_functions)
    for more information. The function should construct and return one of
    the following:
      * A <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object: Outputs of `Dataset` object must be
        a tuple `(features, labels)` with same constraints as below.
      * A tuple `(features, labels)`: Where `features` is a <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> or
        a dictionary of string feature name to `Tensor` and `labels` is a
        `Tensor` or a dictionary of string label name to `Tensor`. Both
        `features` and `labels` are consumed by `model_fn`. They should
        satisfy the expectation of `model_fn` from inputs.
* <b>`hooks`</b>: List of `tf.train.SessionRunHook` subclass instances. Used for
    callbacks inside the training loop.
* <b>`steps`</b>: Number of steps for which to train the model. If `None`, train
    forever or train until `input_fn` generates the `tf.errors.OutOfRange`
    error or `StopIteration` exception. `steps` works incrementally. If you
    call two times `train(steps=10)` then training occurs in total 20 steps.
    If `OutOfRange` or `StopIteration` occurs in the middle, training stops
    before 20 steps. If you don't want to have incremental behavior please
    set `max_steps` instead. If set, `max_steps` must be `None`.
* <b>`max_steps`</b>: Number of total steps for which to train model. If `None`,
    train forever or train until `input_fn` generates the
    `tf.errors.OutOfRange` error or `StopIteration` exception. If set,
    `steps` must be `None`. If `OutOfRange` or `StopIteration` occurs in the
    middle, training stops before `max_steps` steps. Two calls to
    `train(steps=100)` means 200 training iterations. On the other hand, two
    calls to `train(max_steps=100)` means that the second call will not do
    any iteration since first call did all 100 steps.
* <b>`saving_listeners`</b>: list of `CheckpointSaverListener` objects. Used for
    callbacks that run immediately before or after checkpoint savings.


#### Returns:

`self`, for chaining.


#### Raises:

* <b>`ValueError`</b>: If both `steps` and `max_steps` are not `None`.
* <b>`ValueError`</b>: If either `steps` or `max_steps <= 0`.




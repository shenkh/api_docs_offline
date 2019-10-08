<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.BoostedTreesRegressor" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="config"/>
<meta itemprop="property" content="model_dir"/>
<meta itemprop="property" content="model_fn"/>
<meta itemprop="property" content="params"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="eval_dir"/>
<meta itemprop="property" content="evaluate"/>
<meta itemprop="property" content="experimental_export_all_saved_models"/>
<meta itemprop="property" content="experimental_feature_importances"/>
<meta itemprop="property" content="experimental_predict_with_explanations"/>
<meta itemprop="property" content="export_saved_model"/>
<meta itemprop="property" content="export_savedmodel"/>
<meta itemprop="property" content="get_variable_names"/>
<meta itemprop="property" content="get_variable_value"/>
<meta itemprop="property" content="latest_checkpoint"/>
<meta itemprop="property" content="predict"/>
<meta itemprop="property" content="train"/>
</div>

# tf.estimator.BoostedTreesRegressor

## Class `BoostedTreesRegressor`



A Regressor for Tensorflow Boosted Trees models.



#### Eager Compatibility
Estimators can be used while eager execution is enabled. Note that `input_fn`
and all hooks are executed inside a graph context, so they have to be written
to be compatible with graph mode. Note that `input_fn` code using <a href="../../tf/data.md"><code>tf.data</code></a>
generally works in both graph and eager modes.



<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    feature_columns,
    n_batches_per_layer,
    model_dir=None,
    label_dimension=_HOLD_FOR_MULTI_DIM_SUPPORT,
    weight_column=None,
    n_trees=100,
    max_depth=6,
    learning_rate=0.1,
    l1_regularization=0.0,
    l2_regularization=0.0,
    tree_complexity=0.0,
    min_node_weight=0.0,
    config=None,
    center_bias=False,
    pruning_mode='none',
    quantile_sketch_epsilon=0.01,
    train_in_memory=False
)
```

Initializes a `BoostedTreesRegressor` instance.

Example:

```python
bucketized_feature_1 = bucketized_column(
  numeric_column('feature_1'), BUCKET_BOUNDARIES_1)
bucketized_feature_2 = bucketized_column(
  numeric_column('feature_2'), BUCKET_BOUNDARIES_2)

# Need to see a large portion of the data before we can build a layer, for
# example half of data n_batches_per_layer = 0.5 * NUM_EXAMPLES / BATCH_SIZE
regressor = estimator.BoostedTreesRegressor(
    feature_columns=[bucketized_feature_1, bucketized_feature_2],
    n_batches_per_layer=n_batches_per_layer,
    n_trees=100,
    ... <some other params>
)

def input_fn_train():
  ...
  return dataset

regressor.train(input_fn=input_fn_train)

def input_fn_eval():
  ...
  return dataset

metrics = regressor.evaluate(input_fn=input_fn_eval)
```

#### Args:

* <b>`feature_columns`</b>: An iterable containing all the feature columns used by
    the model. All items in the set should be instances of classes derived
    from `FeatureColumn`.
* <b>`n_batches_per_layer`</b>: the number of batches to collect statistics per
    layer. The total number of batches is total number of data divided by
    batch size.
* <b>`model_dir`</b>: Directory to save model parameters, graph and etc. This can
    also be used to load checkpoints from the directory into a estimator to
    continue training a previously saved model.
* <b>`label_dimension`</b>: Number of regression targets per example.
    Multi-dimensional support is not yet implemented.
* <b>`weight_column`</b>: A string or a `NumericColumn` created by
    `tf.fc_old.numeric_column` defining feature column representing weights.
    It is used to downweight or boost examples during training. It will be
    multiplied by the loss of the example. If it is a string, it is used as
    a key to fetch weight tensor from the `features`. If it is a
    `NumericColumn`, raw tensor is fetched by key `weight_column.key`, then
    weight_column.normalizer_fn is applied on it to get weight tensor.
* <b>`n_trees`</b>: number trees to be created.
* <b>`max_depth`</b>: maximum depth of the tree to grow.
* <b>`learning_rate`</b>: shrinkage parameter to be used when a tree added to the
    model.
* <b>`l1_regularization`</b>: regularization multiplier applied to the absolute
    weights of the tree leafs.
* <b>`l2_regularization`</b>: regularization multiplier applied to the square weights
    of the tree leafs.
* <b>`tree_complexity`</b>: regularization factor to penalize trees with more leaves.
* <b>`min_node_weight`</b>: min_node_weight: minimum hessian a node must have for a
    split to be considered. The value will be compared with
    sum(leaf_hessian)/(batch_size * n_batches_per_layer).
* <b>`config`</b>: `RunConfig` object to configure the runtime settings.
* <b>`center_bias`</b>: Whether bias centering needs to occur. Bias centering refers
    to the first node in the very first tree returning the prediction that
    is aligned with the original labels distribution. For example, for
    regression problems, the first node will return the mean of the labels.
    For binary classification problems, it will return a logit for a prior
    probability of label 1.
* <b>`pruning_mode`</b>: one of 'none', 'pre', 'post' to indicate no pruning, pre-
    pruning (do not split a node if not enough gain is observed) and post
    pruning (build the tree up to a max depth and then prune branches with
    negative gain). For pre and post pruning, you MUST provide
    tree_complexity >0.
* <b>`quantile_sketch_epsilon`</b>: float between 0 and 1. Error bound for quantile
    computation. This is only used for float feature columns, and the number
    of buckets generated per float feature is 1/quantile_sketch_epsilon.
* <b>`train_in_memory`</b>: `bool`, when true, it assumes the dataset is in memory,
    i.e., input_fn should return the entire dataset as a single batch,
    n_batches_per_layer should be set as 1, num_worker_replicas should be 1,
    and num_ps_replicas should be 0 in `tf.Estimator.RunConfig`.


#### Raises:

* <b>`ValueError`</b>: when wrong arguments are given or unsupported functionalities
     are requested.



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
- `input_fn` raises an end-of-input exception (<a href="../../tf/errors/OutOfRangeError.md"><code>tf.errors.OutOfRangeError</code></a>
or
`StopIteration`).

#### Args:

* <b>`input_fn`</b>: A function that constructs the input data for evaluation. See
    [Premade Estimators](
    https://tensorflow.org/guide/premade_estimators#create_input_functions)
    for more information. The
    function should construct and return one of the following:  * A
    <a href="../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object: Outputs of `Dataset` object must be a tuple
    `(features, labels)` with same constraints as below. * A tuple
    `(features, labels)`: Where `features` is a <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> or a dictionary
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
(order of preference: <a href="../../tf/estimator/ModeKeys.md#TRAIN"><code>tf.estimator.ModeKeys.TRAIN</code></a>,
<a href="../../tf/estimator/ModeKeys.md#EVAL"><code>tf.estimator.ModeKeys.EVAL</code></a>, then
<a href="../../tf/estimator/ModeKeys.md#PREDICT"><code>tf.estimator.ModeKeys.PREDICT</code></a>), such that up to three
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
<a href="../../tf/estimator/export/ExportOutput.md"><code>tf.estimator.export.ExportOutput</code></a>s, and the inputs are always the input
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
* <b>`input_receiver_fn_map`</b>: dict of <a href="../../tf/estimator/ModeKeys.md"><code>tf.estimator.ModeKeys</code></a> to
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

<h3 id="experimental_feature_importances"><code>experimental_feature_importances</code></h3>

``` python
experimental_feature_importances(normalize=False)
```

Computes gain-based feature importances.

The higher the value, the more important the corresponding feature.

#### Args:

* <b>`normalize`</b>: If True, normalize the feature importances.


#### Returns:

* <b>`feature_importances`</b>: an OrderedDict, where the keys are the feature column
  names and the values are importances. It is sorted by importance.


#### Raises:

* <b>`ValueError`</b>: When attempting to normalize on an empty ensemble
    or an ensemble of trees which have no splits. Or when attempting
    to normalize and feature importances have negative values.

<h3 id="experimental_predict_with_explanations"><code>experimental_predict_with_explanations</code></h3>

``` python
experimental_predict_with_explanations(
    input_fn,
    predict_keys=None,
    hooks=None,
    checkpoint_path=None
)
```

Computes model explainability outputs per example along with predictions.

Currently supports directional feature contributions (DFCs). For each
instance, DFCs indicate the aggregate contribution of each feature. See
https://arxiv.org/abs/1312.1121 and
http://blog.datadive.net/interpreting-random-forests/ for more details.

#### Args:

* <b>`input_fn`</b>: A function that provides input data for predicting as
    minibatches. See [Premade Estimators](
    https://tensorflow.org/guide/premade_estimators#create_input_functions)
      for more information. The function should construct and return one of
    the following:
    * A <a href="../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object: Outputs of `Dataset` object must be a
      tuple `(features, labels)` with same constraints as below.
    * A tuple `(features, labels)`: Where `features` is a <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> or a
      dictionary of string feature name to `Tensor` and `labels` is a
      `Tensor` or a dictionary of string label name to `Tensor`. Both
      `features` and `labels` are consumed by `model_fn`. They should
      satisfy the expectation of `model_fn` from inputs.
* <b>`predict_keys`</b>: list of `str`, name of the keys to predict. It is used if
    the <a href="../../tf/estimator/EstimatorSpec.md#predictions"><code>tf.estimator.EstimatorSpec.predictions</code></a> is a `dict`. If
    `predict_keys` is used then rest of the predictions will be filtered
    from the dictionary, with the exception of 'bias' and 'dfc', which will
    always be in the dictionary. If `None`, returns all keys in prediction
    dict, as well as two new keys 'dfc' and 'bias'.
* <b>`hooks`</b>: List of `tf.train.SessionRunHook` subclass instances. Used for
    callbacks inside the prediction call.
* <b>`checkpoint_path`</b>: Path of a specific checkpoint to predict. If `None`, the
    latest checkpoint in `model_dir` is used.  If there are no checkpoints
    in `model_dir`, prediction is run with newly initialized `Variables`
    instead of ones restored from checkpoint.


#### Yields:

Evaluated values of `predictions` tensors. The `predictions` tensors will
contain at least two keys 'dfc' and 'bias' for model explanations. The
`dfc` value corresponds to the contribution of each feature to the overall
prediction for this instance (positive indicating that the feature makes
it more likely to select class 1 and negative less likely). The `dfc` is
an OrderedDict, where the keys are the feature column names and the values
are the contributions. It is sorted by the absolute value of the
contribution (e.g OrderedDict([('age', -0.54), ('gender', 0.4), ('fare',
0.21)])). The 'bias' value will be the same across all the instances,
corresponding to the probability (classification) or prediction
(regression) of the training data distribution.


#### Raises:

* <b>`ValueError`</b>: when wrong arguments are given or unsupported functionalities
   are requested.

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
<a href="../../tf/estimator/export/ExportOutput.md"><code>tf.estimator.export.ExportOutput</code></a>s, and the inputs are always the input
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
    <a href="../../tf/estimator/export/ServingInputReceiver.md"><code>tf.estimator.export.ServingInputReceiver</code></a> or
    <a href="../../tf/estimator/export/TensorServingInputReceiver.md"><code>tf.estimator.export.TensorServingInputReceiver</code></a>.
* <b>`assets_extra`</b>: A dict specifying how to populate the assets.extra directory
    within the exported `SavedModel`, or `None` if no extra assets are
    needed.
* <b>`as_text`</b>: whether to write the `SavedModel` proto in text format.
* <b>`checkpoint_path`</b>: The checkpoint path to export.  If `None` (the default),
    the most recent checkpoint found within the model directory is chosen.
* <b>`experimental_mode`</b>: <a href="../../tf/estimator/ModeKeys.md"><code>tf.estimator.ModeKeys</code></a> value indicating with mode
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
<a href="../../tf/estimator/export/ExportOutput.md"><code>tf.estimator.export.ExportOutput</code></a>s, and the inputs are always the input
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
    <a href="../../tf/estimator/export/ServingInputReceiver.md"><code>tf.estimator.export.ServingInputReceiver</code></a> or
    <a href="../../tf/estimator/export/TensorServingInputReceiver.md"><code>tf.estimator.export.TensorServingInputReceiver</code></a>.
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
    (<a href="../../tf/errors/OutOfRangeError.md"><code>tf.errors.OutOfRangeError</code></a> or `StopIteration`).
    See [Premade Estimators](
    https://tensorflow.org/guide/premade_estimators#create_input_functions)
    for more information. The function should construct and return one of
    the following:

      * A <a href="../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object: Outputs of `Dataset` object must have
        same constraints as below.
      * features: A <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> or a dictionary of string feature name to
        `Tensor`. features are consumed by `model_fn`. They should satisfy
        the expectation of `model_fn` from inputs.
      * A tuple, in which case the first item is extracted as features.

* <b>`predict_keys`</b>: list of `str`, name of the keys to predict. It is used if
    the <a href="../../tf/estimator/EstimatorSpec.md#predictions"><code>tf.estimator.EstimatorSpec.predictions</code></a> is a `dict`. If
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
    <a href="../../tf/estimator/EstimatorSpec.md#predictions"><code>tf.estimator.EstimatorSpec.predictions</code></a> is not a `dict`.

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
      * A <a href="../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object: Outputs of `Dataset` object must be
        a tuple `(features, labels)` with same constraints as below.
      * A tuple `(features, labels)`: Where `features` is a <a href="../../tf/Tensor.md"><code>tf.Tensor</code></a> or
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




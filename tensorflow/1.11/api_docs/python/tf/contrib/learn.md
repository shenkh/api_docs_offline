<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.learn" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.learn



Defined in [`tensorflow/contrib/learn/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/learn/__init__.py).

High level API for learning (DEPRECATED).

This module and all its submodules are deprecated. See
[contrib/learn/README.md](https://www.tensorflow.org/code/tensorflow/contrib/learn/README.md)
for migration instructions.

See the [Contrib Learn](https://tensorflow.org/api_guides/python/contrib.learn)
guide.







## Modules

[`datasets`](../../tf/contrib/learn/datasets.md) module: Dataset utilities and synthetic/reference datasets (deprecated).

[`graph_actions`](../../tf/contrib/learn/graph_actions.md) module: High level operations on graphs (deprecated).

[`head`](../../tf/contrib/learn/head.md) module: Abstractions for the head(s) of a model (deprecated).

[`io`](../../tf/contrib/learn/io.md) module: Tools to allow different io formats (deprecated).

[`learn_runner`](../../tf/contrib/learn/learn_runner.md) module: Utilities to run and tune an Experiment (deprecated).

[`models`](../../tf/contrib/learn/models.md) module: Various high level TF models (deprecated).

[`monitors`](../../tf/contrib/learn/monitors.md) module: Monitors instrument the training process (deprecated).

[`ops`](../../tf/contrib/learn/ops.md) module: Various TensorFlow Ops (deprecated).

[`preprocessing`](../../tf/contrib/learn/preprocessing.md) module: Preprocessing tools useful for building models (deprecated).

[`utils`](../../tf/contrib/learn/utils.md) module: TensorFlow Learn Utils (deprecated).

## Classes

[`class BaseEstimator`](../../tf/contrib/learn/BaseEstimator.md): Abstract BaseEstimator class to train and evaluate TensorFlow models.

[`class DNNClassifier`](../../tf/contrib/learn/DNNClassifier.md): A classifier for TensorFlow DNN models.

[`class DNNEstimator`](../../tf/contrib/learn/DNNEstimator.md): A Estimator for TensorFlow DNN models with user specified _Head.

[`class DNNLinearCombinedClassifier`](../../tf/contrib/learn/DNNLinearCombinedClassifier.md): A classifier for TensorFlow Linear and DNN joined training models.

[`class DNNLinearCombinedEstimator`](../../tf/contrib/learn/DNNLinearCombinedEstimator.md): An estimator for TensorFlow Linear and DNN joined training models.

[`class DNNLinearCombinedRegressor`](../../tf/contrib/learn/DNNLinearCombinedRegressor.md): A regressor for TensorFlow Linear and DNN joined training models.

[`class DNNRegressor`](../../tf/contrib/learn/DNNRegressor.md): A regressor for TensorFlow DNN models.

[`class DynamicRnnEstimator`](../../tf/contrib/learn/DynamicRnnEstimator.md): Dynamically unrolled RNN (deprecated).

[`class Estimator`](../../tf/contrib/learn/Estimator.md): Estimator class is the basic TensorFlow model trainer/evaluator.

[`class Evaluable`](../../tf/contrib/learn/Evaluable.md): Interface for objects that are evaluatable by, e.g., `Experiment`.

[`class Experiment`](../../tf/contrib/learn/Experiment.md): Experiment is a class containing all information needed to train a model.

[`class ExportStrategy`](../../tf/contrib/learn/ExportStrategy.md): A class representing a type of model export.

[`class Head`](../../tf/contrib/learn/Head.md): Interface for the head/top of a model.

[`class InputFnOps`](../../tf/contrib/learn/InputFnOps.md): A return type for an input_fn (deprecated).

[`class KMeansClustering`](../../tf/contrib/learn/KMeansClustering.md): An Estimator for K-Means clustering.

[`class LinearClassifier`](../../tf/contrib/learn/LinearClassifier.md): Linear classifier model.

[`class LinearEstimator`](../../tf/contrib/learn/LinearEstimator.md): Linear model with user specified head.

[`class LinearRegressor`](../../tf/contrib/learn/LinearRegressor.md): Linear regressor model.

[`class MetricSpec`](../../tf/contrib/learn/MetricSpec.md): MetricSpec connects a model to metric functions.

[`class ModeKeys`](../../tf/contrib/learn/ModeKeys.md): Standard names for model modes (deprecated).

[`class ModelFnOps`](../../tf/contrib/learn/ModelFnOps.md): Ops returned from a model_fn.

[`class NanLossDuringTrainingError`](../../tf/contrib/learn/NanLossDuringTrainingError.md): Unspecified run-time error.

[`class NotFittedError`](../../tf/contrib/learn/NotFittedError.md): Exception class to raise if estimator is used before fitting.

[`class PredictionKey`](../../tf/contrib/learn/PredictionKey.md): THIS CLASS IS DEPRECATED.

[`class ProblemType`](../../tf/contrib/learn/ProblemType.md): Enum-like values for the type of problem that the model solves.

[`class RunConfig`](../../tf/contrib/learn/RunConfig.md): This class specifies the configurations for an `Estimator` run.

[`class SKCompat`](../../tf/contrib/learn/SKCompat.md): Scikit learn wrapper for TensorFlow Learn Estimator.

[`class SVM`](../../tf/contrib/learn/SVM.md): Support Vector Machine (SVM) model for binary classification.

[`class TaskType`](../../tf/contrib/learn/TaskType.md): DEPRECATED CLASS.

[`class Trainable`](../../tf/contrib/learn/Trainable.md): Interface for objects that are trainable by, e.g., `Experiment`.

## Functions

[`LogisticRegressor(...)`](../../tf/contrib/learn/LogisticRegressor.md): Builds a logistic regression Estimator for binary classification.

[`binary_svm_head(...)`](../../tf/contrib/learn/binary_svm_head.md): Creates a `Head` for binary classification with SVMs. (deprecated)

[`build_parsing_serving_input_fn(...)`](../../tf/contrib/learn/build_parsing_serving_input_fn.md): Build an input_fn appropriate for serving, expecting fed tf.Examples. (deprecated)

[`evaluate(...)`](../../tf/contrib/learn/evaluate.md): Evaluate a model loaded from a checkpoint. (deprecated)

[`extract_dask_data(...)`](../../tf/contrib/learn/extract_dask_data.md): Extract data from dask.Series or dask.DataFrame for predictors. (deprecated)

[`extract_dask_labels(...)`](../../tf/contrib/learn/extract_dask_labels.md): Extract data from dask.Series or dask.DataFrame for labels. (deprecated)

[`extract_pandas_data(...)`](../../tf/contrib/learn/extract_pandas_data.md): Extract data from pandas.DataFrame for predictors. (deprecated)

[`extract_pandas_labels(...)`](../../tf/contrib/learn/extract_pandas_labels.md): Extract data from pandas.DataFrame for labels. (deprecated)

[`extract_pandas_matrix(...)`](../../tf/contrib/learn/extract_pandas_matrix.md): Extracts numpy matrix from pandas DataFrame. (deprecated)

[`infer(...)`](../../tf/contrib/learn/infer.md): Restore graph from `restore_checkpoint_path` and run `output_dict` tensors. (deprecated)

[`infer_real_valued_columns_from_input(...)`](../../tf/contrib/learn/infer_real_valued_columns_from_input.md): Creates `FeatureColumn` objects for inputs defined by input `x`. (deprecated)

[`infer_real_valued_columns_from_input_fn(...)`](../../tf/contrib/learn/infer_real_valued_columns_from_input_fn.md): Creates `FeatureColumn` objects for inputs defined by `input_fn`. (deprecated)

[`make_export_strategy(...)`](../../tf/contrib/learn/make_export_strategy.md): Create an ExportStrategy for use with Experiment. (deprecated)

[`multi_class_head(...)`](../../tf/contrib/learn/multi_class_head.md): Creates a `Head` for multi class single label classification. (deprecated)

[`multi_head(...)`](../../tf/contrib/learn/multi_head.md): Creates a MultiHead stemming from same logits/hidden layer. (deprecated)

[`multi_label_head(...)`](../../tf/contrib/learn/multi_label_head.md): Creates a Head for multi label classification. (deprecated)

[`no_op_train_fn(...)`](../../tf/contrib/learn/no_op_train_fn.md): DEPRECATED FUNCTION

[`poisson_regression_head(...)`](../../tf/contrib/learn/poisson_regression_head.md): Creates a `Head` for poisson regression. (deprecated)

[`read_batch_examples(...)`](../../tf/contrib/learn/read_batch_examples.md): Adds operations to read, queue, batch `Example` protos. (deprecated)

[`read_batch_features(...)`](../../tf/contrib/learn/read_batch_features.md): Adds operations to read, queue, batch and parse `Example` protos. (deprecated)

[`read_batch_record_features(...)`](../../tf/contrib/learn/read_batch_record_features.md): Reads TFRecord, queues, batches and parses `Example` proto. (deprecated)

[`read_keyed_batch_examples(...)`](../../tf/contrib/learn/read_keyed_batch_examples.md): Adds operations to read, queue, batch `Example` protos. (deprecated)

[`read_keyed_batch_examples_shared_queue(...)`](../../tf/contrib/learn/read_keyed_batch_examples_shared_queue.md): Adds operations to read, queue, batch `Example` protos. (deprecated)

[`read_keyed_batch_features(...)`](../../tf/contrib/learn/read_keyed_batch_features.md): Adds operations to read, queue, batch and parse `Example` protos. (deprecated)

[`read_keyed_batch_features_shared_queue(...)`](../../tf/contrib/learn/read_keyed_batch_features_shared_queue.md): Adds operations to read, queue, batch and parse `Example` protos. (deprecated)

[`regression_head(...)`](../../tf/contrib/learn/regression_head.md): Creates a `Head` for linear regression. (deprecated)

[`run_feeds(...)`](../../tf/contrib/learn/run_feeds.md): See run_feeds_iter(). Returns a `list` instead of an iterator. (deprecated)

[`run_n(...)`](../../tf/contrib/learn/run_n.md): Run `output_dict` tensors `n` times, with the same `feed_dict` each run. (deprecated)

[`train(...)`](../../tf/contrib/learn/train.md): Train a model. (deprecated)


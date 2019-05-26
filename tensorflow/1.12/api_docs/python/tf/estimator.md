<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.estimator



Defined in [`tensorflow/python/estimator/api/estimator/__init__.py`](/code/stable/tensorflow/python/estimator/api/estimator/__init__.py).

Estimator: High level tools for working with models.

## Modules

[`export`](../tf/estimator/export.md) module: Utility methods for exporting Estimator.

[`inputs`](../tf/estimator/inputs.md) module: Utility methods to create simple input_fns.

## Classes

[`class BaselineClassifier`](../tf/estimator/BaselineClassifier.md): A classifier that can establish a simple baseline.

[`class BaselineRegressor`](../tf/estimator/BaselineRegressor.md): A regressor that can establish a simple baseline.

[`class BestExporter`](../tf/estimator/BestExporter.md): This class exports the serving graph and checkpoints of the best models.

[`class BoostedTreesClassifier`](../tf/estimator/BoostedTreesClassifier.md): A Classifier for Tensorflow Boosted Trees models.

[`class BoostedTreesRegressor`](../tf/estimator/BoostedTreesRegressor.md): A Regressor for Tensorflow Boosted Trees models.

[`class DNNClassifier`](../tf/estimator/DNNClassifier.md): A classifier for TensorFlow DNN models.

[`class DNNLinearCombinedClassifier`](../tf/estimator/DNNLinearCombinedClassifier.md): An estimator for TensorFlow Linear and DNN joined classification models.

[`class DNNLinearCombinedRegressor`](../tf/estimator/DNNLinearCombinedRegressor.md): An estimator for TensorFlow Linear and DNN joined models for regression.

[`class DNNRegressor`](../tf/estimator/DNNRegressor.md): A regressor for TensorFlow DNN models.

[`class Estimator`](../tf/estimator/Estimator.md): Estimator class to train and evaluate TensorFlow models.

[`class EstimatorSpec`](../tf/estimator/EstimatorSpec.md): Ops and objects returned from a `model_fn` and passed to an `Estimator`.

[`class EvalSpec`](../tf/estimator/EvalSpec.md): Configuration for the "eval" part for the `train_and_evaluate` call.

[`class Exporter`](../tf/estimator/Exporter.md): A class representing a type of model export.

[`class FinalExporter`](../tf/estimator/FinalExporter.md): This class exports the serving graph and checkpoints in the end.

[`class LatestExporter`](../tf/estimator/LatestExporter.md): This class regularly exports the serving graph and checkpoints.

[`class LinearClassifier`](../tf/estimator/LinearClassifier.md): Linear classifier model.

[`class LinearRegressor`](../tf/estimator/LinearRegressor.md): An estimator for TensorFlow Linear regression problems.

[`class ModeKeys`](../tf/estimator/ModeKeys.md): Standard names for model modes.

[`class RunConfig`](../tf/estimator/RunConfig.md): This class specifies the configurations for an `Estimator` run.

[`class TrainSpec`](../tf/estimator/TrainSpec.md): Configuration for the "train" part for the `train_and_evaluate` call.

[`class VocabInfo`](../tf/train/VocabInfo.md): Vocabulary information for warm-starting.

[`class WarmStartSettings`](../tf/estimator/WarmStartSettings.md): Settings for warm-starting in `tf.estimator.Estimators`.

## Functions

[`classifier_parse_example_spec(...)`](../tf/estimator/classifier_parse_example_spec.md): Generates parsing spec for tf.parse_example to be used with classifiers.

[`regressor_parse_example_spec(...)`](../tf/estimator/regressor_parse_example_spec.md): Generates parsing spec for tf.parse_example to be used with regressors.

[`train_and_evaluate(...)`](../tf/estimator/train_and_evaluate.md): Train and evaluate the `estimator`.


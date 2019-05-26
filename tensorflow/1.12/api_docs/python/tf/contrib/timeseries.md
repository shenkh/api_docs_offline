<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.timeseries" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.timeseries



Defined in [`tensorflow/contrib/timeseries/__init__.py`](/code/stable/tensorflow/contrib/timeseries/__init__.py).

A time series library in TensorFlow (TFTS).






## Modules

[`saved_model_utils`](../../tf/contrib/timeseries/saved_model_utils.md) module: Convenience functions for working with time series saved_models.

## Classes

[`class ARModel`](../../tf/contrib/timeseries/ARModel.md): Auto-regressive model, both linear and non-linear.

[`class ARRegressor`](../../tf/contrib/timeseries/ARRegressor.md): An Estimator for an (optionally non-linear) autoregressive model.

[`class CSVReader`](../../tf/contrib/timeseries/CSVReader.md): Reads from a collection of CSV-formatted files.

[`class FilteringResults`](../../tf/contrib/timeseries/FilteringResults.md): Keys returned from evaluation/filtering.

[`class NumpyReader`](../../tf/contrib/timeseries/NumpyReader.md): A time series parser for feeding Numpy arrays to a `TimeSeriesInputFn`.

[`class OneShotPredictionHead`](../../tf/contrib/timeseries/OneShotPredictionHead.md): A time series head which exports a single stateless serving signature.

[`class RandomWindowInputFn`](../../tf/contrib/timeseries/RandomWindowInputFn.md): Wraps a `TimeSeriesReader` to create random batches of windows.

[`class StructuralEnsembleRegressor`](../../tf/contrib/timeseries/StructuralEnsembleRegressor.md): An Estimator for structural time series models.

[`class TimeSeriesRegressor`](../../tf/contrib/timeseries/TimeSeriesRegressor.md): An Estimator to fit and evaluate a time series model.

[`class TrainEvalFeatures`](../../tf/contrib/timeseries/TrainEvalFeatures.md): Feature names used during training and evaluation.

[`class WholeDatasetInputFn`](../../tf/contrib/timeseries/WholeDatasetInputFn.md): Supports passing a full time series to a model for evaluation/inference.

## Functions

[`predict_continuation_input_fn(...)`](../../tf/contrib/timeseries/predict_continuation_input_fn.md): An Estimator input_fn for running predict() after evaluate().


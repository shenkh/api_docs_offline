<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.metrics" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.metrics

### Aliases:

* Module `tf.keras.metrics`
* Module `tf.metrics`



Defined in [`tensorflow/python/keras/api/_v2/keras/metrics/__init__.py`](/code/stable/tensorflow/python/keras/api/_v2/keras/metrics/__init__.py).

Built-in metrics.

## Classes

[`class AUC`](../tf/metrics/AUC.md): Computes the approximate AUC (Area under the curve) via a Riemann sum.

[`class Accuracy`](../tf/metrics/Accuracy.md): Calculates how often predictions matches labels.

[`class BinaryAccuracy`](../tf/metrics/BinaryAccuracy.md): Calculates how often predictions matches labels.

[`class BinaryCrossentropy`](../tf/metrics/BinaryCrossentropy.md): Computes the crossentropy metric between the labels and predictions.

[`class CategoricalAccuracy`](../tf/metrics/CategoricalAccuracy.md): Calculates how often predictions matches labels.

[`class CategoricalCrossentropy`](../tf/metrics/CategoricalCrossentropy.md): Computes the crossentropy metric between the labels and predictions.

[`class CategoricalHinge`](../tf/metrics/CategoricalHinge.md): Computes the categorical hinge metric between `y_true` and `y_pred`.

[`class CosineSimilarity`](../tf/metrics/CosineSimilarity.md): Computes the cosine similarity between the labels and predictions.

[`class FalseNegatives`](../tf/metrics/FalseNegatives.md): Calculates the number of false negatives.

[`class FalsePositives`](../tf/metrics/FalsePositives.md): Calculates the number of false positives.

[`class Hinge`](../tf/metrics/Hinge.md): Computes the hinge metric between `y_true` and `y_pred`.

[`class KLDivergence`](../tf/metrics/KLDivergence.md): Computes Kullback-Leibler divergence metric between `y_true` and `y_pred`.

[`class LogCoshError`](../tf/metrics/LogCoshError.md): Computes the logarithm of the hyperbolic cosine of the prediction error.

[`class Mean`](../tf/metrics/Mean.md): Computes the (weighted) mean of the given values.

[`class MeanAbsoluteError`](../tf/metrics/MeanAbsoluteError.md): Computes the mean absolute error between the labels and predictions.

[`class MeanAbsolutePercentageError`](../tf/metrics/MeanAbsolutePercentageError.md): Computes the mean absolute percentage error between `y_true` and `y_pred`.

[`class MeanIoU`](../tf/metrics/MeanIoU.md): Computes the mean Intersection-Over-Union metric.

[`class MeanRelativeError`](../tf/metrics/MeanRelativeError.md): Computes the mean relative error by normalizing with the given values.

[`class MeanSquaredError`](../tf/metrics/MeanSquaredError.md): Computes the mean squared error between `y_true` and `y_pred`.

[`class MeanSquaredLogarithmicError`](../tf/metrics/MeanSquaredLogarithmicError.md): Computes the mean squared logarithmic error between `y_true` and `y_pred`.

[`class MeanTensor`](../tf/metrics/MeanTensor.md): Computes the element-wise (weighted) mean of the given tensors.

[`class Metric`](../tf/metrics/Metric.md): Encapsulates metric logic and state.

[`class Poisson`](../tf/metrics/Poisson.md): Computes the Poisson metric between `y_true` and `y_pred`.

[`class Precision`](../tf/metrics/Precision.md): Computes the precision of the predictions with respect to the labels.

[`class Recall`](../tf/metrics/Recall.md): Computes the recall of the predictions with respect to the labels.

[`class RootMeanSquaredError`](../tf/metrics/RootMeanSquaredError.md): Computes root mean squared error metric between `y_true` and `y_pred`.

[`class SensitivityAtSpecificity`](../tf/metrics/SensitivityAtSpecificity.md): Computes the sensitivity at a given specificity.

[`class SparseCategoricalAccuracy`](../tf/metrics/SparseCategoricalAccuracy.md): Calculates how often predictions matches integer labels.

[`class SparseCategoricalCrossentropy`](../tf/metrics/SparseCategoricalCrossentropy.md): Computes the crossentropy metric between the labels and predictions.

[`class SparseTopKCategoricalAccuracy`](../tf/metrics/SparseTopKCategoricalAccuracy.md): Computes how often integer targets are in the top `K` predictions.

[`class SpecificityAtSensitivity`](../tf/metrics/SpecificityAtSensitivity.md): Computes the specificity at a given sensitivity.

[`class SquaredHinge`](../tf/metrics/SquaredHinge.md): Computes the squared hinge metric between `y_true` and `y_pred`.

[`class Sum`](../tf/metrics/Sum.md): Computes the (weighted) sum of the given values.

[`class TopKCategoricalAccuracy`](../tf/metrics/TopKCategoricalAccuracy.md): Computes how often targets are in the top `K` predictions.

[`class TrueNegatives`](../tf/metrics/TrueNegatives.md): Calculates the number of true negatives.

[`class TruePositives`](../tf/metrics/TruePositives.md): Calculates the number of true positives.

## Functions

[`KLD(...)`](../tf/losses/KLD.md): Computes Kullback-Leibler divergence loss between `y_true` and `y_pred`.

[`MAE(...)`](../tf/losses/MAE.md)

[`MAPE(...)`](../tf/losses/MAPE.md)

[`MSE(...)`](../tf/losses/MSE.md)

[`MSLE(...)`](../tf/losses/MSLE.md)

[`binary_accuracy(...)`](../tf/metrics/binary_accuracy.md)

[`binary_crossentropy(...)`](../tf/losses/binary_crossentropy.md)

[`categorical_accuracy(...)`](../tf/metrics/categorical_accuracy.md)

[`categorical_crossentropy(...)`](../tf/losses/categorical_crossentropy.md): Computes the categorical crossentropy loss.

[`deserialize(...)`](../tf/metrics/deserialize.md)

[`get(...)`](../tf/metrics/get.md)

[`hinge(...)`](../tf/losses/hinge.md): Computes the hinge loss between `y_true` and `y_pred`.

[`kld(...)`](../tf/losses/KLD.md): Computes Kullback-Leibler divergence loss between `y_true` and `y_pred`.

[`kullback_leibler_divergence(...)`](../tf/losses/KLD.md): Computes Kullback-Leibler divergence loss between `y_true` and `y_pred`.

[`mae(...)`](../tf/losses/MAE.md)

[`mape(...)`](../tf/losses/MAPE.md)

[`mean_absolute_error(...)`](../tf/losses/MAE.md)

[`mean_absolute_percentage_error(...)`](../tf/losses/MAPE.md)

[`mean_squared_error(...)`](../tf/losses/MSE.md)

[`mean_squared_logarithmic_error(...)`](../tf/losses/MSLE.md)

[`mse(...)`](../tf/losses/MSE.md)

[`msle(...)`](../tf/losses/MSLE.md)

[`poisson(...)`](../tf/losses/poisson.md): Computes the Poisson loss between y_true and y_pred.

[`serialize(...)`](../tf/metrics/serialize.md)

[`sparse_categorical_accuracy(...)`](../tf/metrics/sparse_categorical_accuracy.md)

[`sparse_categorical_crossentropy(...)`](../tf/losses/sparse_categorical_crossentropy.md)

[`sparse_top_k_categorical_accuracy(...)`](../tf/metrics/sparse_top_k_categorical_accuracy.md)

[`squared_hinge(...)`](../tf/losses/squared_hinge.md): Computes the squared hinge loss between `y_true` and `y_pred`.

[`top_k_categorical_accuracy(...)`](../tf/metrics/top_k_categorical_accuracy.md)


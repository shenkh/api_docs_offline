<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.keras.metrics

Built-in metrics.

### Aliases:

* Module `tf.compat.v2.keras.metrics`
* Module `tf.compat.v2.metrics`
* Module `tf.keras.metrics`
* Module `tf.metrics`



Defined in [`python/keras/api/_v2/keras/metrics/__init__.py`](/code/stable/tensorflow/python/keras/api/_v2/keras/metrics/__init__.py).

<!-- Placeholder for "Used in" -->


## Classes

[`class AUC`](../../tf/keras/metrics/AUC.md): Computes the approximate AUC (Area under the curve) via a Riemann sum.

[`class Accuracy`](../../tf/keras/metrics/Accuracy.md): Calculates how often predictions matches labels.

[`class BinaryAccuracy`](../../tf/keras/metrics/BinaryAccuracy.md): Calculates how often predictions matches labels.

[`class BinaryCrossentropy`](../../tf/keras/metrics/BinaryCrossentropy.md): Computes the crossentropy metric between the labels and predictions.

[`class CategoricalAccuracy`](../../tf/keras/metrics/CategoricalAccuracy.md): Calculates how often predictions matches labels.

[`class CategoricalCrossentropy`](../../tf/keras/metrics/CategoricalCrossentropy.md): Computes the crossentropy metric between the labels and predictions.

[`class CategoricalHinge`](../../tf/keras/metrics/CategoricalHinge.md): Computes the categorical hinge metric between `y_true` and `y_pred`.

[`class CosineSimilarity`](../../tf/keras/metrics/CosineSimilarity.md): Computes the cosine similarity between the labels and predictions.

[`class FalseNegatives`](../../tf/keras/metrics/FalseNegatives.md): Calculates the number of false negatives.

[`class FalsePositives`](../../tf/keras/metrics/FalsePositives.md): Calculates the number of false positives.

[`class Hinge`](../../tf/keras/metrics/Hinge.md): Computes the hinge metric between `y_true` and `y_pred`.

[`class KLDivergence`](../../tf/keras/metrics/KLDivergence.md): Computes Kullback-Leibler divergence metric between `y_true` and `y_pred`.

[`class LogCoshError`](../../tf/keras/metrics/LogCoshError.md): Computes the logarithm of the hyperbolic cosine of the prediction error.

[`class Mean`](../../tf/keras/metrics/Mean.md): Computes the (weighted) mean of the given values.

[`class MeanAbsoluteError`](../../tf/keras/metrics/MeanAbsoluteError.md): Computes the mean absolute error between the labels and predictions.

[`class MeanAbsolutePercentageError`](../../tf/keras/metrics/MeanAbsolutePercentageError.md): Computes the mean absolute percentage error between `y_true` and `y_pred`.

[`class MeanIoU`](../../tf/keras/metrics/MeanIoU.md): Computes the mean Intersection-Over-Union metric.

[`class MeanRelativeError`](../../tf/keras/metrics/MeanRelativeError.md): Computes the mean relative error by normalizing with the given values.

[`class MeanSquaredError`](../../tf/keras/metrics/MeanSquaredError.md): Computes the mean squared error between `y_true` and `y_pred`.

[`class MeanSquaredLogarithmicError`](../../tf/keras/metrics/MeanSquaredLogarithmicError.md): Computes the mean squared logarithmic error between `y_true` and `y_pred`.

[`class MeanTensor`](../../tf/keras/metrics/MeanTensor.md): Computes the element-wise (weighted) mean of the given tensors.

[`class Metric`](../../tf/keras/metrics/Metric.md): Encapsulates metric logic and state.

[`class Poisson`](../../tf/keras/metrics/Poisson.md): Computes the Poisson metric between `y_true` and `y_pred`.

[`class Precision`](../../tf/keras/metrics/Precision.md): Computes the precision of the predictions with respect to the labels.

[`class Recall`](../../tf/keras/metrics/Recall.md): Computes the recall of the predictions with respect to the labels.

[`class RootMeanSquaredError`](../../tf/keras/metrics/RootMeanSquaredError.md): Computes root mean squared error metric between `y_true` and `y_pred`.

[`class SensitivityAtSpecificity`](../../tf/keras/metrics/SensitivityAtSpecificity.md): Computes the sensitivity at a given specificity.

[`class SparseCategoricalAccuracy`](../../tf/keras/metrics/SparseCategoricalAccuracy.md): Calculates how often predictions matches integer labels.

[`class SparseCategoricalCrossentropy`](../../tf/keras/metrics/SparseCategoricalCrossentropy.md): Computes the crossentropy metric between the labels and predictions.

[`class SparseTopKCategoricalAccuracy`](../../tf/keras/metrics/SparseTopKCategoricalAccuracy.md): Computes how often integer targets are in the top `K` predictions.

[`class SpecificityAtSensitivity`](../../tf/keras/metrics/SpecificityAtSensitivity.md): Computes the specificity at a given sensitivity.

[`class SquaredHinge`](../../tf/keras/metrics/SquaredHinge.md): Computes the squared hinge metric between `y_true` and `y_pred`.

[`class Sum`](../../tf/keras/metrics/Sum.md): Computes the (weighted) sum of the given values.

[`class TopKCategoricalAccuracy`](../../tf/keras/metrics/TopKCategoricalAccuracy.md): Computes how often targets are in the top `K` predictions.

[`class TrueNegatives`](../../tf/keras/metrics/TrueNegatives.md): Calculates the number of true negatives.

[`class TruePositives`](../../tf/keras/metrics/TruePositives.md): Calculates the number of true positives.

## Functions

[`KLD(...)`](../../tf/keras/losses/KLD.md)

[`MAE(...)`](../../tf/keras/losses/MAE.md)

[`MAPE(...)`](../../tf/keras/losses/MAPE.md)

[`MSE(...)`](../../tf/keras/losses/MSE.md)

[`MSLE(...)`](../../tf/keras/losses/MSLE.md)

[`binary_accuracy(...)`](../../tf/keras/metrics/binary_accuracy.md)

[`binary_crossentropy(...)`](../../tf/keras/losses/binary_crossentropy.md)

[`categorical_accuracy(...)`](../../tf/keras/metrics/categorical_accuracy.md)

[`categorical_crossentropy(...)`](../../tf/keras/losses/categorical_crossentropy.md): Computes the categorical crossentropy loss.

[`deserialize(...)`](../../tf/keras/metrics/deserialize.md)

[`get(...)`](../../tf/keras/metrics/get.md)

[`hinge(...)`](../../tf/keras/losses/hinge.md): Computes the hinge loss between `y_true` and `y_pred`.

[`kld(...)`](../../tf/keras/losses/KLD.md)

[`kullback_leibler_divergence(...)`](../../tf/keras/losses/KLD.md)

[`mae(...)`](../../tf/keras/losses/MAE.md)

[`mape(...)`](../../tf/keras/losses/MAPE.md)

[`mean_absolute_error(...)`](../../tf/keras/losses/MAE.md)

[`mean_absolute_percentage_error(...)`](../../tf/keras/losses/MAPE.md)

[`mean_squared_error(...)`](../../tf/keras/losses/MSE.md)

[`mean_squared_logarithmic_error(...)`](../../tf/keras/losses/MSLE.md)

[`mse(...)`](../../tf/keras/losses/MSE.md)

[`msle(...)`](../../tf/keras/losses/MSLE.md)

[`poisson(...)`](../../tf/keras/losses/poisson.md): Computes the Poisson loss between y_true and y_pred.

[`serialize(...)`](../../tf/keras/metrics/serialize.md)

[`sparse_categorical_accuracy(...)`](../../tf/keras/metrics/sparse_categorical_accuracy.md)

[`sparse_categorical_crossentropy(...)`](../../tf/keras/losses/sparse_categorical_crossentropy.md)

[`sparse_top_k_categorical_accuracy(...)`](../../tf/keras/metrics/sparse_top_k_categorical_accuracy.md)

[`squared_hinge(...)`](../../tf/keras/losses/squared_hinge.md): Computes the squared hinge loss between `y_true` and `y_pred`.

[`top_k_categorical_accuracy(...)`](../../tf/keras/metrics/top_k_categorical_accuracy.md)


<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.feature_column" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.feature_column



Defined in [`tensorflow/feature_column/__init__.py`](https://www.tensorflow.org/code/tensorflow/feature_column/__init__.py).

Public API for tf.feature_column namespace.

## Functions

[`bucketized_column(...)`](../tf/feature_column/bucketized_column.md): Represents discretized dense input.

[`categorical_column_with_hash_bucket(...)`](../tf/feature_column/categorical_column_with_hash_bucket.md): Represents sparse feature where ids are set by hashing.

[`categorical_column_with_identity(...)`](../tf/feature_column/categorical_column_with_identity.md): A `_CategoricalColumn` that returns identity values.

[`categorical_column_with_vocabulary_file(...)`](../tf/feature_column/categorical_column_with_vocabulary_file.md): A `_CategoricalColumn` with a vocabulary file.

[`categorical_column_with_vocabulary_list(...)`](../tf/feature_column/categorical_column_with_vocabulary_list.md): A `_CategoricalColumn` with in-memory vocabulary.

[`crossed_column(...)`](../tf/feature_column/crossed_column.md): Returns a column for performing crosses of categorical features.

[`embedding_column(...)`](../tf/feature_column/embedding_column.md): `_DenseColumn` that converts from sparse, categorical input.

[`indicator_column(...)`](../tf/feature_column/indicator_column.md): Represents multi-hot representation of given categorical column.

[`input_layer(...)`](../tf/feature_column/input_layer.md): Returns a dense `Tensor` as input layer based on given `feature_columns`.

[`linear_model(...)`](../tf/feature_column/linear_model.md): Returns a linear prediction `Tensor` based on given `feature_columns`.

[`make_parse_example_spec(...)`](../tf/feature_column/make_parse_example_spec.md): Creates parsing spec dictionary from input feature_columns.

[`numeric_column(...)`](../tf/feature_column/numeric_column.md): Represents real valued or numerical features.

[`shared_embedding_columns(...)`](../tf/feature_column/shared_embedding_columns.md): List of dense columns that convert from sparse, categorical input.

[`weighted_categorical_column(...)`](../tf/feature_column/weighted_categorical_column.md): Applies weight values to a `_CategoricalColumn`.


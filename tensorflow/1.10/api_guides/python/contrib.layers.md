# Layers (contrib)
[TOC]

Ops for building neural network layers, regularizers, summaries, etc.

<h2 id="Higher_level_ops_for_building_neural_network_layers">Higher level ops for building neural network layers</h2>

This package provides several ops that take care of creating variables that are
used internally in a consistent way and provide the building blocks for many
common machine learning algorithms.

*   <a href="../../api_docs/python/tf/contrib/layers/avg_pool2d.md"><code>tf.contrib.layers.avg_pool2d</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/batch_norm.md"><code>tf.contrib.layers.batch_norm</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/conv2d.md"><code>tf.contrib.layers.convolution2d</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/conv2d_in_plane.md"><code>tf.contrib.layers.conv2d_in_plane</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/conv2d_in_plane.md"><code>tf.contrib.layers.convolution2d_in_plane</code></a>
*   <a href="../../api_docs/python/tf/nn/conv2d_transpose.md"><code>tf.nn.conv2d_transpose</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/conv2d_transpose.md"><code>tf.contrib.layers.convolution2d_transpose</code></a>
*   <a href="../../api_docs/python/tf/nn/dropout.md"><code>tf.nn.dropout</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/flatten.md"><code>tf.contrib.layers.flatten</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/fully_connected.md"><code>tf.contrib.layers.fully_connected</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/layer_norm.md"><code>tf.contrib.layers.layer_norm</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/max_pool2d.md"><code>tf.contrib.layers.max_pool2d</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/one_hot_encoding.md"><code>tf.contrib.layers.one_hot_encoding</code></a>
*   <a href="../../api_docs/python/tf/nn/relu.md"><code>tf.nn.relu</code></a>
*   <a href="../../api_docs/python/tf/nn/relu6.md"><code>tf.nn.relu6</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/repeat.md"><code>tf.contrib.layers.repeat</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/safe_embedding_lookup_sparse.md"><code>tf.contrib.layers.safe_embedding_lookup_sparse</code></a>
*   <a href="../../api_docs/python/tf/nn/separable_conv2d.md"><code>tf.nn.separable_conv2d</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/separable_conv2d.md"><code>tf.contrib.layers.separable_convolution2d</code></a>
*   <a href="../../api_docs/python/tf/nn/softmax.md"><code>tf.nn.softmax</code></a>
*   <a href="../../api_docs/python/tf/stack.md"><code>tf.stack</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/unit_norm.md"><code>tf.contrib.layers.unit_norm</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/embed_sequence.md"><code>tf.contrib.layers.embed_sequence</code></a>

Aliases for fully_connected which set a default activation function are
available: `relu`, `relu6` and `linear`.

`stack` operation is also available. It builds a stack of layers by applying
a layer repeatedly.

<h2 id="Regularizers">Regularizers</h2>

Regularization can help prevent overfitting. These have the signature
`fn(weights)`. The loss is typically added to
<a href="../../api_docs/python/tf/GraphKeys.md#REGULARIZATION_LOSSES"><code>tf.GraphKeys.REGULARIZATION_LOSSES</code></a>.

*   <a href="../../api_docs/python/tf/contrib/layers/apply_regularization.md"><code>tf.contrib.layers.apply_regularization</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/l1_regularizer.md"><code>tf.contrib.layers.l1_regularizer</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/l2_regularizer.md"><code>tf.contrib.layers.l2_regularizer</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/sum_regularizer.md"><code>tf.contrib.layers.sum_regularizer</code></a>

<h2 id="Initializers">Initializers</h2>

Initializers are used to initialize variables with sensible values given their
size, data type, and purpose.

*   <a href="../../api_docs/python/tf/contrib/layers/xavier_initializer.md"><code>tf.contrib.layers.xavier_initializer</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/xavier_initializer.md"><code>tf.contrib.layers.xavier_initializer_conv2d</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/variance_scaling_initializer.md"><code>tf.contrib.layers.variance_scaling_initializer</code></a>

<h2 id="Optimization">Optimization</h2>

Optimize weights given a loss.

*   <a href="../../api_docs/python/tf/contrib/layers/optimize_loss.md"><code>tf.contrib.layers.optimize_loss</code></a>

<h2 id="Summaries">Summaries</h2>

Helper functions to summarize specific variables or ops.

*   <a href="../../api_docs/python/tf/contrib/layers/summarize_activation.md"><code>tf.contrib.layers.summarize_activation</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/summarize_tensor.md"><code>tf.contrib.layers.summarize_tensor</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/summarize_tensors.md"><code>tf.contrib.layers.summarize_tensors</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/summarize_collection.md"><code>tf.contrib.layers.summarize_collection</code></a>

The layers module defines convenience functions `summarize_variables`,
`summarize_weights` and `summarize_biases`, which set the `collection` argument
of `summarize_collection` to `VARIABLES`, `WEIGHTS` and `BIASES`, respectively.

*   <a href="../../api_docs/python/tf/contrib/layers/summarize_activations.md"><code>tf.contrib.layers.summarize_activations</code></a>

<h2 id="Feature_columns">Feature columns</h2>

Feature columns provide a mechanism to map data to a model.

*   <a href="../../api_docs/python/tf/contrib/layers/bucketized_column.md"><code>tf.contrib.layers.bucketized_column</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/check_feature_columns.md"><code>tf.contrib.layers.check_feature_columns</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/create_feature_spec_for_parsing.md"><code>tf.contrib.layers.create_feature_spec_for_parsing</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/crossed_column.md"><code>tf.contrib.layers.crossed_column</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/embedding_column.md"><code>tf.contrib.layers.embedding_column</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/scattered_embedding_column.md"><code>tf.contrib.layers.scattered_embedding_column</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/input_from_feature_columns.md"><code>tf.contrib.layers.input_from_feature_columns</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/joint_weighted_sum_from_feature_columns.md"><code>tf.contrib.layers.joint_weighted_sum_from_feature_columns</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/make_place_holder_tensors_for_base_features.md"><code>tf.contrib.layers.make_place_holder_tensors_for_base_features</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/multi_class_target.md"><code>tf.contrib.layers.multi_class_target</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/one_hot_column.md"><code>tf.contrib.layers.one_hot_column</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/parse_feature_columns_from_examples.md"><code>tf.contrib.layers.parse_feature_columns_from_examples</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/parse_feature_columns_from_sequence_examples.md"><code>tf.contrib.layers.parse_feature_columns_from_sequence_examples</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/real_valued_column.md"><code>tf.contrib.layers.real_valued_column</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/shared_embedding_columns.md"><code>tf.contrib.layers.shared_embedding_columns</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/sparse_column_with_hash_bucket.md"><code>tf.contrib.layers.sparse_column_with_hash_bucket</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/sparse_column_with_integerized_feature.md"><code>tf.contrib.layers.sparse_column_with_integerized_feature</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/sparse_column_with_keys.md"><code>tf.contrib.layers.sparse_column_with_keys</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/sparse_column_with_vocabulary_file.md"><code>tf.contrib.layers.sparse_column_with_vocabulary_file</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/weighted_sparse_column.md"><code>tf.contrib.layers.weighted_sparse_column</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/weighted_sum_from_feature_columns.md"><code>tf.contrib.layers.weighted_sum_from_feature_columns</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/infer_real_valued_columns.md"><code>tf.contrib.layers.infer_real_valued_columns</code></a>
*   <a href="../../api_docs/python/tf/contrib/layers/sequence_input_from_feature_columns.md"><code>tf.contrib.layers.sequence_input_from_feature_columns</code></a>

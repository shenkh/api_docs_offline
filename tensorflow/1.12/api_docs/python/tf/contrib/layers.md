<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="OPTIMIZER_CLS_NAMES"/>
<meta itemprop="property" content="OPTIMIZER_SUMMARIES"/>
<meta itemprop="property" content="SPARSE_FEATURE_CROSS_DEFAULT_HASH_KEY"/>
<meta itemprop="property" content="elu"/>
<meta itemprop="property" content="legacy_linear"/>
<meta itemprop="property" content="legacy_relu"/>
<meta itemprop="property" content="linear"/>
<meta itemprop="property" content="relu"/>
<meta itemprop="property" content="relu6"/>
<meta itemprop="property" content="scale_gradient"/>
</div>

# Module: tf.contrib.layers



Defined in [`tensorflow/contrib/layers/__init__.py`](/code/stable/tensorflow/contrib/layers/__init__.py).

Ops for building neural network layers, regularizers, summaries, etc.

See the
[Contrib Layers](https://tensorflow.org/api_guides/python/contrib.layers)
guide.









## Modules

[`feature_column`](../../tf/contrib/layers/feature_column.md) module: This API defines FeatureColumn abstraction.

[`summaries`](../../tf/contrib/layers/summaries.md) module: Utility functions for summary creation.

## Classes

[`class GDN`](../../tf/contrib/layers/GDN.md): Generalized divisive normalization layer.

[`class RevBlock`](../../tf/contrib/layers/RevBlock.md): Block of reversible layers. See rev_block.

## Functions

[`apply_regularization(...)`](../../tf/contrib/layers/apply_regularization.md): Returns the summed penalty by applying `regularizer` to the `weights_list`.

[`avg_pool2d(...)`](../../tf/contrib/layers/avg_pool2d.md): Adds a 2D average pooling op.

[`avg_pool3d(...)`](../../tf/contrib/layers/avg_pool3d.md): Adds a 3D average pooling op.

[`batch_norm(...)`](../../tf/contrib/layers/batch_norm.md): Adds a Batch Normalization layer from http://arxiv.org/abs/1502.03167.

[`bias_add(...)`](../../tf/contrib/layers/bias_add.md): Adds a bias to the inputs.

[`bow_encoder(...)`](../../tf/contrib/layers/bow_encoder.md): Maps a sequence of symbols to a vector per example by averaging embeddings.

[`bucketized_column(...)`](../../tf/contrib/layers/bucketized_column.md): Creates a _BucketizedColumn for discretizing dense input.

[`check_feature_columns(...)`](../../tf/contrib/layers/check_feature_columns.md): Checks the validity of the set of FeatureColumns.

[`conv1d(...)`](../../tf/contrib/layers/conv1d.md): Adds an N-D convolution followed by an optional batch_norm layer.

[`conv2d(...)`](../../tf/contrib/layers/conv2d.md): Adds an N-D convolution followed by an optional batch_norm layer.

[`conv2d_in_plane(...)`](../../tf/contrib/layers/conv2d_in_plane.md): Performs the same in-plane convolution to each channel independently.

[`conv2d_transpose(...)`](../../tf/contrib/layers/conv2d_transpose.md): Adds a convolution2d_transpose with an optional batch normalization layer.

[`conv3d(...)`](../../tf/contrib/layers/conv3d.md): Adds an N-D convolution followed by an optional batch_norm layer.

[`conv3d_transpose(...)`](../../tf/contrib/layers/conv3d_transpose.md): Adds a convolution3d_transpose with an optional batch normalization layer.

[`convolution(...)`](../../tf/contrib/layers/convolution.md): Adds an N-D convolution followed by an optional batch_norm layer.

[`convolution1d(...)`](../../tf/contrib/layers/conv1d.md): Adds an N-D convolution followed by an optional batch_norm layer.

[`convolution2d(...)`](../../tf/contrib/layers/conv2d.md): Adds an N-D convolution followed by an optional batch_norm layer.

[`convolution2d_in_plane(...)`](../../tf/contrib/layers/conv2d_in_plane.md): Performs the same in-plane convolution to each channel independently.

[`convolution2d_transpose(...)`](../../tf/contrib/layers/conv2d_transpose.md): Adds a convolution2d_transpose with an optional batch normalization layer.

[`convolution3d(...)`](../../tf/contrib/layers/conv3d.md): Adds an N-D convolution followed by an optional batch_norm layer.

[`convolution3d_transpose(...)`](../../tf/contrib/layers/conv3d_transpose.md): Adds a convolution3d_transpose with an optional batch normalization layer.

[`create_feature_spec_for_parsing(...)`](../../tf/contrib/layers/create_feature_spec_for_parsing.md): Helper that prepares features config from input feature_columns.

[`crossed_column(...)`](../../tf/contrib/layers/crossed_column.md): Creates a _CrossedColumn for performing feature crosses.

[`dense_to_sparse(...)`](../../tf/contrib/layers/dense_to_sparse.md): Converts a dense tensor into a sparse tensor.

[`dropout(...)`](../../tf/contrib/layers/dropout.md): Returns a dropout op applied to the input.

[`embed_sequence(...)`](../../tf/contrib/layers/embed_sequence.md): Maps a sequence of symbols to a sequence of embeddings.

[`embedding_column(...)`](../../tf/contrib/layers/embedding_column.md): Creates an `_EmbeddingColumn` for feeding sparse data into a DNN.

[`embedding_lookup_unique(...)`](../../tf/contrib/layers/embedding_lookup_unique.md): Version of embedding_lookup that avoids duplicate lookups.

[`flatten(...)`](../../tf/contrib/layers/flatten.md): Flattens the input while maintaining the batch_size.

[`fully_connected(...)`](../../tf/contrib/layers/fully_connected.md): Adds a fully connected layer.

[`gdn(...)`](../../tf/contrib/layers/gdn.md): Functional interface for GDN layer.

[`group_norm(...)`](../../tf/contrib/layers/group_norm.md): Functional interface for the group normalization layer.

[`images_to_sequence(...)`](../../tf/contrib/layers/images_to_sequence.md): Convert a batch of images into a batch of sequences.

[`infer_real_valued_columns(...)`](../../tf/contrib/layers/infer_real_valued_columns.md)

[`input_from_feature_columns(...)`](../../tf/contrib/layers/input_from_feature_columns.md): A tf.contrib.layers style input layer builder based on FeatureColumns.

[`instance_norm(...)`](../../tf/contrib/layers/instance_norm.md): Functional interface for the instance normalization layer.

[`joint_weighted_sum_from_feature_columns(...)`](../../tf/contrib/layers/joint_weighted_sum_from_feature_columns.md): A restricted linear prediction builder based on FeatureColumns.

[`l1_l2_regularizer(...)`](../../tf/contrib/layers/l1_l2_regularizer.md): Returns a function that can be used to apply L1 L2 regularizations.

[`l1_regularizer(...)`](../../tf/contrib/layers/l1_regularizer.md): Returns a function that can be used to apply L1 regularization to weights.

[`l2_regularizer(...)`](../../tf/contrib/layers/l2_regularizer.md): Returns a function that can be used to apply L2 regularization to weights.

[`layer_norm(...)`](../../tf/contrib/layers/layer_norm.md): Adds a Layer Normalization layer.

[`legacy_fully_connected(...)`](../../tf/contrib/layers/legacy_fully_connected.md): Adds the parameters for a fully connected layer and returns the output.

[`make_place_holder_tensors_for_base_features(...)`](../../tf/contrib/layers/make_place_holder_tensors_for_base_features.md): Returns placeholder tensors for inference.

[`max_pool2d(...)`](../../tf/contrib/layers/max_pool2d.md): Adds a 2D Max Pooling op.

[`max_pool3d(...)`](../../tf/contrib/layers/max_pool3d.md): Adds a 3D Max Pooling op.

[`maxout(...)`](../../tf/contrib/layers/maxout.md): Adds a maxout op from https://arxiv.org/abs/1302.4389

[`multi_class_target(...)`](../../tf/contrib/layers/multi_class_target.md): Creates a _TargetColumn for multi class single label classification. (deprecated)

[`one_hot_column(...)`](../../tf/contrib/layers/one_hot_column.md): Creates an `_OneHotColumn` for a one-hot or multi-hot repr in a DNN.

[`one_hot_encoding(...)`](../../tf/contrib/layers/one_hot_encoding.md): Transform numeric labels into onehot_labels using <a href="../../tf/one_hot.md"><code>tf.one_hot</code></a>.

[`optimize_loss(...)`](../../tf/contrib/layers/optimize_loss.md): Given loss and parameters for optimizer, returns a training op.

[`parse_feature_columns_from_examples(...)`](../../tf/contrib/layers/parse_feature_columns_from_examples.md): Parses tf.Examples to extract tensors for given feature_columns.

[`parse_feature_columns_from_sequence_examples(...)`](../../tf/contrib/layers/parse_feature_columns_from_sequence_examples.md): Parses tf.SequenceExamples to extract tensors for given `FeatureColumn`s.

[`real_valued_column(...)`](../../tf/contrib/layers/real_valued_column.md): Creates a `_RealValuedColumn` for dense numeric data.

[`recompute_grad(...)`](../../tf/contrib/layers/recompute_grad.md): Decorator that recomputes the function on the backwards pass.

[`regression_target(...)`](../../tf/contrib/layers/regression_target.md): Creates a _TargetColumn for linear regression. (deprecated)

[`repeat(...)`](../../tf/contrib/layers/repeat.md): Applies the same layer with the same arguments repeatedly.

[`rev_block(...)`](../../tf/contrib/layers/rev_block.md): A block of reversible residual layers.

[`safe_embedding_lookup_sparse(...)`](../../tf/contrib/layers/safe_embedding_lookup_sparse.md): Lookup embedding results, accounting for invalid IDs and empty features.

[`scattered_embedding_column(...)`](../../tf/contrib/layers/scattered_embedding_column.md): Creates an embedding column of a sparse feature using parameter hashing.

[`separable_conv2d(...)`](../../tf/contrib/layers/separable_conv2d.md): Adds a depth-separable 2D convolution with optional batch_norm layer.

[`separable_convolution2d(...)`](../../tf/contrib/layers/separable_conv2d.md): Adds a depth-separable 2D convolution with optional batch_norm layer.

[`sequence_input_from_feature_columns(...)`](../../tf/contrib/layers/sequence_input_from_feature_columns.md): Builds inputs for sequence models from `FeatureColumn`s. (experimental)

[`sequence_to_images(...)`](../../tf/contrib/layers/sequence_to_images.md): Convert a batch of sequences into a batch of images.

[`shared_embedding_columns(...)`](../../tf/contrib/layers/shared_embedding_columns.md): Creates a list of `_EmbeddingColumn` sharing the same embedding.

[`softmax(...)`](../../tf/contrib/layers/softmax.md): Performs softmax on Nth dimension of N-dimensional logit tensor.

[`sparse_column_with_hash_bucket(...)`](../../tf/contrib/layers/sparse_column_with_hash_bucket.md): Creates a _SparseColumn with hashed bucket configuration.

[`sparse_column_with_integerized_feature(...)`](../../tf/contrib/layers/sparse_column_with_integerized_feature.md): Creates an integerized _SparseColumn.

[`sparse_column_with_keys(...)`](../../tf/contrib/layers/sparse_column_with_keys.md): Creates a _SparseColumn with keys.

[`sparse_column_with_vocabulary_file(...)`](../../tf/contrib/layers/sparse_column_with_vocabulary_file.md): Creates a _SparseColumn with vocabulary file configuration.

[`spatial_softmax(...)`](../../tf/contrib/layers/spatial_softmax.md): Computes the spatial softmax of a convolutional feature map.

[`stack(...)`](../../tf/contrib/layers/stack.md): Builds a stack of layers by applying layer repeatedly using stack_args.

[`sum_regularizer(...)`](../../tf/contrib/layers/sum_regularizer.md): Returns a function that applies the sum of multiple regularizers.

[`summarize_activation(...)`](../../tf/contrib/layers/summarize_activation.md): Summarize an activation.

[`summarize_activations(...)`](../../tf/contrib/layers/summarize_activations.md): Summarize activations, using `summarize_activation` to summarize.

[`summarize_collection(...)`](../../tf/contrib/layers/summarize_collection.md): Summarize a graph collection of tensors, possibly filtered by name.

[`summarize_tensor(...)`](../../tf/contrib/layers/summarize_tensor.md): Summarize a tensor using a suitable summary type.

[`summarize_tensors(...)`](../../tf/contrib/layers/summarize_tensors.md): Summarize a set of tensors.

[`transform_features(...)`](../../tf/contrib/layers/transform_features.md): Returns transformed features based on features columns passed in.

[`unit_norm(...)`](../../tf/contrib/layers/unit_norm.md): Normalizes the given input across the specified dimension to unit length.

[`variance_scaling_initializer(...)`](../../tf/contrib/layers/variance_scaling_initializer.md): Returns an initializer that generates tensors without scaling variance.

[`weighted_sparse_column(...)`](../../tf/contrib/layers/weighted_sparse_column.md): Creates a _SparseColumn by combining sparse_id_column with a weight column.

[`weighted_sum_from_feature_columns(...)`](../../tf/contrib/layers/weighted_sum_from_feature_columns.md): A tf.contrib.layers style linear prediction builder based on FeatureColumn.

[`xavier_initializer(...)`](../../tf/contrib/layers/xavier_initializer.md): Returns an initializer performing "Xavier" initialization for weights.

[`xavier_initializer_conv2d(...)`](../../tf/contrib/layers/xavier_initializer.md): Returns an initializer performing "Xavier" initialization for weights.

## Other Members

<h3 id="OPTIMIZER_CLS_NAMES"><code>OPTIMIZER_CLS_NAMES</code></h3>

<h3 id="OPTIMIZER_SUMMARIES"><code>OPTIMIZER_SUMMARIES</code></h3>

<h3 id="SPARSE_FEATURE_CROSS_DEFAULT_HASH_KEY"><code>SPARSE_FEATURE_CROSS_DEFAULT_HASH_KEY</code></h3>

<h3 id="elu"><code>elu</code></h3>

<h3 id="legacy_linear"><code>legacy_linear</code></h3>

<h3 id="legacy_relu"><code>legacy_relu</code></h3>

<h3 id="linear"><code>linear</code></h3>

<h3 id="relu"><code>relu</code></h3>

<h3 id="relu6"><code>relu6</code></h3>

<h3 id="scale_gradient"><code>scale_gradient</code></h3>


<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.model_pruning" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.model_pruning



Defined in [`tensorflow/contrib/model_pruning/__init__.py`](/code/stable/tensorflow/contrib/model_pruning/__init__.py).

Model pruning implementation in tensorflow.

## Classes

[`class MaskedBasicLSTMCell`](../../tf/contrib/model_pruning/MaskedBasicLSTMCell.md): Basic LSTM recurrent network cell with pruning.

[`class MaskedLSTMCell`](../../tf/contrib/model_pruning/MaskedLSTMCell.md): LSTMCell with pruning.

[`class Pruning`](../../tf/contrib/model_pruning/Pruning.md)

## Functions

[`apply_mask(...)`](../../tf/contrib/model_pruning/apply_mask.md): Apply mask to a given weight tensor.

[`get_masked_weights(...)`](../../tf/contrib/model_pruning/get_masked_weights.md)

[`get_masks(...)`](../../tf/contrib/model_pruning/get_masks.md)

[`get_pruning_hparams(...)`](../../tf/contrib/model_pruning/get_pruning_hparams.md): Get a tf.HParams object with the default values for the hyperparameters.

[`get_thresholds(...)`](../../tf/contrib/model_pruning/get_thresholds.md)

[`get_weight_sparsity(...)`](../../tf/contrib/model_pruning/get_weight_sparsity.md): Get sparsity of the weights.

[`get_weights(...)`](../../tf/contrib/model_pruning/get_weights.md)

[`graph_def_from_checkpoint(...)`](../../tf/contrib/model_pruning/graph_def_from_checkpoint.md): Converts checkpoint data to GraphDef.

[`masked_conv2d(...)`](../../tf/contrib/model_pruning/masked_conv2d.md): Adds an 2D convolution followed by an optional batch_norm layer.

[`masked_convolution(...)`](../../tf/contrib/model_pruning/masked_conv2d.md): Adds an 2D convolution followed by an optional batch_norm layer.

[`masked_fully_connected(...)`](../../tf/contrib/model_pruning/masked_fully_connected.md): Adds a sparse fully connected layer. The weight matrix is masked.

[`strip_pruning_vars_fn(...)`](../../tf/contrib/model_pruning/strip_pruning_vars_fn.md): Removes mask variable from the graph.

[`train(...)`](../../tf/contrib/model_pruning/train.md): Wrapper around tf-slim's train function.


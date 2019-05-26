<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.saved_model" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.saved_model



Defined in [`tensorflow/_api/v1/saved_model/__init__.py`](/code/stable/tensorflow/_api/v1/saved_model/__init__.py).

Public API for tf.saved_model namespace.

## Modules

[`builder`](../tf/saved_model/builder.md) module: SavedModel builder.

[`constants`](../tf/saved_model/constants.md) module: Constants for SavedModel save and restore operations.

[`loader`](../tf/saved_model/loader.md) module: Loader functionality for SavedModel with hermetic, language-neutral exports.

[`main_op`](../tf/saved_model/main_op.md) module: SavedModel main op.

[`signature_constants`](../tf/saved_model/signature_constants.md) module: Signature constants for SavedModel save and restore operations.

[`signature_def_utils`](../tf/saved_model/signature_def_utils.md) module: SignatureDef utility functions.

[`tag_constants`](../tf/saved_model/tag_constants.md) module: Common tags used for graphs in SavedModel.

[`utils`](../tf/saved_model/utils.md) module: SavedModel utility functions.

## Classes

[`class Builder`](../tf/saved_model/Builder.md): Builds the `SavedModel` protocol buffer and saves variables and assets.

## Functions

[`build_signature_def(...)`](../tf/saved_model/build_signature_def.md): Utility function to build a SignatureDef protocol buffer.

[`build_tensor_info(...)`](../tf/saved_model/build_tensor_info.md): Utility function to build TensorInfo proto.

[`classification_signature_def(...)`](../tf/saved_model/classification_signature_def.md): Creates classification signature from given examples and predictions.

[`get_tensor_from_tensor_info(...)`](../tf/saved_model/get_tensor_from_tensor_info.md): Returns the Tensor or SparseTensor described by a TensorInfo proto.

[`is_valid_signature(...)`](../tf/saved_model/is_valid_signature.md): Determine whether a SignatureDef can be served by TensorFlow Serving.

[`load(...)`](../tf/saved_model/load.md): Loads the model from a SavedModel as specified by tags.

[`main_op_with_restore(...)`](../tf/saved_model/main_op_with_restore.md): Returns a main op to init variables, tables and restore the graph.

[`maybe_saved_model_directory(...)`](../tf/saved_model/maybe_saved_model_directory.md): Checks whether the provided export directory could contain a SavedModel.

[`predict_signature_def(...)`](../tf/saved_model/predict_signature_def.md): Creates prediction signature from given inputs and outputs.

[`regression_signature_def(...)`](../tf/saved_model/regression_signature_def.md): Creates regression signature from given examples and predictions.

[`simple_save(...)`](../tf/saved_model/simple_save.md): Convenience function to build a SavedModel suitable for serving.


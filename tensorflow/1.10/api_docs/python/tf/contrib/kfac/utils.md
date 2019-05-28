<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.utils" />
</div>

# Module: tf.contrib.kfac.utils



Defined in [`tensorflow/contrib/kfac/python/ops/utils_lib.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/utils_lib.py).

Utility functions.

## Classes

[`class SequenceDict`](../../../tf/contrib/kfac/utils/SequenceDict.md): A dict convenience wrapper that allows getting/setting with sequences.

[`class SubGraph`](../../../tf/contrib/kfac/utils/SubGraph.md): Defines a subgraph given by all the dependencies of a given set of outputs.

## Functions

[`batch_execute(...)`](../../../tf/contrib/kfac/utils/batch_execute.md): Executes a subset of ops per global step.

[`column_to_tensors(...)`](../../../tf/contrib/kfac/utils/column_to_tensors.md): Converts a column vector back to the shape of the given template.

[`ensure_sequence(...)`](../../../tf/contrib/kfac/utils/ensure_sequence.md): If `obj` isn't a tuple or list, return a tuple containing `obj`.

[`extract_convolution_patches(...)`](../../../tf/contrib/kfac/utils/extract_convolution_patches.md): Extracts inputs to each output coordinate in tf.nn.convolution.

[`extract_pointwise_conv2d_patches(...)`](../../../tf/contrib/kfac/utils/extract_pointwise_conv2d_patches.md): Extract patches for a 1x1 conv2d.

[`fwd_gradients(...)`](../../../tf/contrib/kfac/utils/fwd_gradients.md): Compute forward-mode gradients.

[`generate_random_signs(...)`](../../../tf/contrib/kfac/utils/generate_random_signs.md): Generate a random tensor with {-1, +1} entries.

[`is_data_format_channel_last(...)`](../../../tf/contrib/kfac/utils/is_data_format_channel_last.md): True if data_format puts channel last.

[`kronecker_product(...)`](../../../tf/contrib/kfac/utils/kronecker_product.md): Computes the Kronecker product two matrices.

[`layer_params_to_mat2d(...)`](../../../tf/contrib/kfac/utils/layer_params_to_mat2d.md): Converts a vector shaped like layer parameters to a 2D matrix.

[`mat2d_to_layer_params(...)`](../../../tf/contrib/kfac/utils/mat2d_to_layer_params.md): Converts a canonical 2D matrix representation back to a vector.

[`matmul_diag_sparse(...)`](../../../tf/contrib/kfac/utils/matmul_diag_sparse.md): Computes matmul(A, B) where A is a diagonal matrix, B is sparse.

[`matmul_sparse_dense(...)`](../../../tf/contrib/kfac/utils/matmul_sparse_dense.md): Computes matmul(A, B) where A is sparse, B is dense.

[`posdef_inv(...)`](../../../tf/contrib/kfac/utils/posdef_inv.md): Computes the inverse of tensor + damping * identity.

[`posdef_inv_cholesky(...)`](../../../tf/contrib/kfac/utils/posdef_inv_cholesky.md): Computes inverse(tensor + damping * identity) with Cholesky.

[`posdef_inv_matrix_inverse(...)`](../../../tf/contrib/kfac/utils/posdef_inv_matrix_inverse.md): Computes inverse(tensor + damping * identity) directly.

[`set_global_constants(...)`](../../../tf/contrib/kfac/utils/set_global_constants.md): Sets various global constants used by the classes in this module.

[`tensors_to_column(...)`](../../../tf/contrib/kfac/utils/tensors_to_column.md): Converts a tensor or list of tensors to a column vector.


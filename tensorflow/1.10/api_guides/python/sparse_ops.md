# Sparse Tensors

Note: Functions taking `Tensor` arguments can also take anything accepted by
<a href="../../api_docs/python/tf/convert_to_tensor.md"><code>tf.convert_to_tensor</code></a>.

[TOC]

<h2 id="Sparse_Tensor_Representation">Sparse Tensor Representation</h2>

TensorFlow supports a `SparseTensor` representation for data that is sparse
in multiple dimensions. Contrast this representation with `IndexedSlices`,
which is efficient for representing tensors that are sparse in their first
dimension, and dense along all other dimensions.

*   <a href="../../api_docs/python/tf/SparseTensor.md"><code>tf.SparseTensor</code></a>
*   <a href="../../api_docs/python/tf/SparseTensorValue.md"><code>tf.SparseTensorValue</code></a>

<h2 id="Conversion">Conversion</h2>

*   <a href="../../api_docs/python/tf/sparse_to_dense.md"><code>tf.sparse_to_dense</code></a>
*   <a href="../../api_docs/python/tf/sparse_tensor_to_dense.md"><code>tf.sparse_tensor_to_dense</code></a>
*   <a href="../../api_docs/python/tf/sparse_to_indicator.md"><code>tf.sparse_to_indicator</code></a>
*   <a href="../../api_docs/python/tf/sparse_merge.md"><code>tf.sparse_merge</code></a>

<h2 id="Manipulation">Manipulation</h2>

*   <a href="../../api_docs/python/tf/sparse_concat.md"><code>tf.sparse_concat</code></a>
*   <a href="../../api_docs/python/tf/sparse_reorder.md"><code>tf.sparse_reorder</code></a>
*   <a href="../../api_docs/python/tf/sparse_reshape.md"><code>tf.sparse_reshape</code></a>
*   <a href="../../api_docs/python/tf/sparse_split.md"><code>tf.sparse_split</code></a>
*   <a href="../../api_docs/python/tf/sparse_retain.md"><code>tf.sparse_retain</code></a>
*   <a href="../../api_docs/python/tf/sparse_reset_shape.md"><code>tf.sparse_reset_shape</code></a>
*   <a href="../../api_docs/python/tf/sparse_fill_empty_rows.md"><code>tf.sparse_fill_empty_rows</code></a>
*   <a href="../../api_docs/python/tf/sparse_transpose.md"><code>tf.sparse_transpose</code></a>

<h2 id="Reduction">Reduction</h2>
*   <a href="../../api_docs/python/tf/sparse_reduce_sum.md"><code>tf.sparse_reduce_sum</code></a>
*   <a href="../../api_docs/python/tf/sparse_reduce_sum_sparse.md"><code>tf.sparse_reduce_sum_sparse</code></a>

<h2 id="Math_Operations">Math Operations</h2>
*   <a href="../../api_docs/python/tf/sparse_add.md"><code>tf.sparse_add</code></a>
*   <a href="../../api_docs/python/tf/sparse_softmax.md"><code>tf.sparse_softmax</code></a>
*   <a href="../../api_docs/python/tf/sparse_tensor_dense_matmul.md"><code>tf.sparse_tensor_dense_matmul</code></a>
*   <a href="../../api_docs/python/tf/sparse_maximum.md"><code>tf.sparse_maximum</code></a>
*   <a href="../../api_docs/python/tf/sparse_minimum.md"><code>tf.sparse_minimum</code></a>

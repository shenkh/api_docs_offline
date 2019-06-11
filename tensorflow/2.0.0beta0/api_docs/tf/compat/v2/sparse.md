<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v2.sparse" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.compat.v2.sparse

Sparse Tensor Representation.

<!-- Placeholder for "Used in" -->

See also <a href="../../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a>.

## Classes

[`class SparseTensor`](../../../tf/sparse/SparseTensor.md): Represents a sparse tensor.

## Functions

[`add(...)`](../../../tf/sparse/add.md): Adds two tensors, at least one of each is a `SparseTensor`.

[`concat(...)`](../../../tf/sparse/concat.md): Concatenates a list of `SparseTensor` along the specified dimension. (deprecated arguments)

[`cross(...)`](../../../tf/sparse/cross.md): Generates sparse cross from a list of sparse and dense tensors.

[`cross_hashed(...)`](../../../tf/sparse/cross_hashed.md): Generates hashed sparse cross from a list of sparse and dense tensors.

[`expand_dims(...)`](../../../tf/sparse/expand_dims.md): Inserts a dimension of 1 into a tensor's shape.

[`eye(...)`](../../../tf/sparse/eye.md): Creates a two-dimensional sparse tensor with ones along the diagonal.

[`fill_empty_rows(...)`](../../../tf/sparse/fill_empty_rows.md): Fills empty rows in the input 2-D `SparseTensor` with a default value.

[`mask(...)`](../../../tf/sparse/mask.md): Masks elements of `IndexedSlices`.

[`maximum(...)`](../../../tf/sparse/maximum.md): Returns the element-wise max of two SparseTensors.

[`minimum(...)`](../../../tf/sparse/minimum.md): Returns the element-wise min of two SparseTensors.

[`reduce_max(...)`](../../../tf/sparse/reduce_max.md): Computes the max of elements across dimensions of a SparseTensor.

[`reduce_sum(...)`](../../../tf/sparse/reduce_sum.md): Computes the sum of elements across dimensions of a SparseTensor.

[`reorder(...)`](../../../tf/sparse/reorder.md): Reorders a `SparseTensor` into the canonical, row-major ordering.

[`reset_shape(...)`](../../../tf/sparse/reset_shape.md): Resets the shape of a `SparseTensor` with indices and values unchanged.

[`reshape(...)`](../../../tf/sparse/reshape.md): Reshapes a `SparseTensor` to represent values in a new dense shape.

[`retain(...)`](../../../tf/sparse/retain.md): Retains specified non-empty values within a `SparseTensor`.

[`segment_mean(...)`](../../../tf/sparse/segment_mean.md): Computes the mean along sparse segments of a tensor.

[`segment_sqrt_n(...)`](../../../tf/sparse/segment_sqrt_n.md): Computes the sum along sparse segments of a tensor divided by the sqrt(N).

[`segment_sum(...)`](../../../tf/sparse/segment_sum.md): Computes the sum along sparse segments of a tensor.

[`slice(...)`](../../../tf/sparse/slice.md): Slice a `SparseTensor` based on the `start` and `size.

[`softmax(...)`](../../../tf/sparse/softmax.md): Applies softmax to a batched N-D `SparseTensor`.

[`sparse_dense_matmul(...)`](../../../tf/sparse/sparse_dense_matmul.md): Multiply SparseTensor (of rank 2) "A" by dense matrix "B".

[`split(...)`](../../../tf/sparse/split.md): Split a `SparseTensor` into `num_split` tensors along `axis`.

[`to_dense(...)`](../../../tf/sparse/to_dense.md): Converts a `SparseTensor` into a dense tensor.

[`to_indicator(...)`](../../../tf/sparse/to_indicator.md): Converts a `SparseTensor` of ids into a dense bool indicator tensor.

[`transpose(...)`](../../../tf/sparse/transpose.md): Transposes a `SparseTensor`


# Math

Note: Functions taking `Tensor` arguments can also take anything accepted by
<a href="../../api_docs/python/tf/convert_to_tensor.md"><code>tf.convert_to_tensor</code></a>.

[TOC]

Note: Elementwise binary operations in TensorFlow follow [numpy-style
broadcasting](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html).

<h2 id="Arithmetic_Operators">Arithmetic Operators</h2>

TensorFlow provides several operations that you can use to add basic arithmetic
operators to your graph.

*   <a href="../../api_docs/python/tf/math/add.md"><code>tf.add</code></a>
*   <a href="../../api_docs/python/tf/subtract.md"><code>tf.subtract</code></a>
*   <a href="../../api_docs/python/tf/multiply.md"><code>tf.multiply</code></a>
*   <a href="../../api_docs/python/tf/scalar_mul.md"><code>tf.scalar_mul</code></a>
*   <a href="../../api_docs/python/tf/div.md"><code>tf.div</code></a>
*   <a href="../../api_docs/python/tf/divide.md"><code>tf.divide</code></a>
*   <a href="../../api_docs/python/tf/truediv.md"><code>tf.truediv</code></a>
*   <a href="../../api_docs/python/tf/floordiv.md"><code>tf.floordiv</code></a>
*   <a href="../../api_docs/python/tf/realdiv.md"><code>tf.realdiv</code></a>
*   <a href="../../api_docs/python/tf/truncatediv.md"><code>tf.truncatediv</code></a>
*   <a href="../../api_docs/python/tf/floor_div.md"><code>tf.floor_div</code></a>
*   <a href="../../api_docs/python/tf/div_no_nan.md"><code>tf.div_no_nan</code></a>
*   <a href="../../api_docs/python/tf/truncatemod.md"><code>tf.truncatemod</code></a>
*   <a href="../../api_docs/python/tf/floormod.md"><code>tf.floormod</code></a>
*   <a href="../../api_docs/python/tf/floormod.md"><code>tf.mod</code></a>
*   <a href="../../api_docs/python/tf/linalg/cross.md"><code>tf.cross</code></a>

<h2 id="Basic_Math_Functions">Basic Math Functions</h2>

TensorFlow provides several operations that you can use to add basic
mathematical functions to your graph.

*   <a href="../../api_docs/python/tf/add_n.md"><code>tf.add_n</code></a>
*   <a href="../../api_docs/python/tf/abs.md"><code>tf.abs</code></a>
*   <a href="../../api_docs/python/tf/negative.md"><code>tf.negative</code></a>
*   <a href="../../api_docs/python/tf/sign.md"><code>tf.sign</code></a>
*   <a href="../../api_docs/python/tf/math/reciprocal.md"><code>tf.reciprocal</code></a>
*   <a href="../../api_docs/python/tf/square.md"><code>tf.square</code></a>
*   <a href="../../api_docs/python/tf/round.md"><code>tf.round</code></a>
*   <a href="../../api_docs/python/tf/sqrt.md"><code>tf.sqrt</code></a>
*   <a href="../../api_docs/python/tf/math/rsqrt.md"><code>tf.rsqrt</code></a>
*   <a href="../../api_docs/python/tf/pow.md"><code>tf.pow</code></a>
*   <a href="../../api_docs/python/tf/math/exp.md"><code>tf.exp</code></a>
*   <a href="../../api_docs/python/tf/math/expm1.md"><code>tf.expm1</code></a>
*   <a href="../../api_docs/python/tf/math/log.md"><code>tf.log</code></a>
*   <a href="../../api_docs/python/tf/math/log1p.md"><code>tf.log1p</code></a>
*   <a href="../../api_docs/python/tf/math/ceil.md"><code>tf.ceil</code></a>
*   <a href="../../api_docs/python/tf/math/floor.md"><code>tf.floor</code></a>
*   <a href="../../api_docs/python/tf/math/maximum.md"><code>tf.maximum</code></a>
*   <a href="../../api_docs/python/tf/math/minimum.md"><code>tf.minimum</code></a>
*   <a href="../../api_docs/python/tf/math/cos.md"><code>tf.cos</code></a>
*   <a href="../../api_docs/python/tf/math/sin.md"><code>tf.sin</code></a>
*   <a href="../../api_docs/python/tf/lbeta.md"><code>tf.lbeta</code></a>
*   <a href="../../api_docs/python/tf/math/tan.md"><code>tf.tan</code></a>
*   <a href="../../api_docs/python/tf/math/acos.md"><code>tf.acos</code></a>
*   <a href="../../api_docs/python/tf/math/asin.md"><code>tf.asin</code></a>
*   <a href="../../api_docs/python/tf/math/atan.md"><code>tf.atan</code></a>
*   <a href="../../api_docs/python/tf/math/cosh.md"><code>tf.cosh</code></a>
*   <a href="../../api_docs/python/tf/math/sinh.md"><code>tf.sinh</code></a>
*   <a href="../../api_docs/python/tf/math/asinh.md"><code>tf.asinh</code></a>
*   <a href="../../api_docs/python/tf/math/acosh.md"><code>tf.acosh</code></a>
*   <a href="../../api_docs/python/tf/math/atanh.md"><code>tf.atanh</code></a>
*   <a href="../../api_docs/python/tf/math/lgamma.md"><code>tf.lgamma</code></a>
*   <a href="../../api_docs/python/tf/math/digamma.md"><code>tf.digamma</code></a>
*   <a href="../../api_docs/python/tf/erf.md"><code>tf.erf</code></a>
*   <a href="../../api_docs/python/tf/math/erfc.md"><code>tf.erfc</code></a>
*   <a href="../../api_docs/python/tf/math/squared_difference.md"><code>tf.squared_difference</code></a>
*   <a href="../../api_docs/python/tf/math/igamma.md"><code>tf.igamma</code></a>
*   <a href="../../api_docs/python/tf/math/igammac.md"><code>tf.igammac</code></a>
*   <a href="../../api_docs/python/tf/math/zeta.md"><code>tf.zeta</code></a>
*   <a href="../../api_docs/python/tf/math/polygamma.md"><code>tf.polygamma</code></a>
*   <a href="../../api_docs/python/tf/math/betainc.md"><code>tf.betainc</code></a>
*   <a href="../../api_docs/python/tf/math/rint.md"><code>tf.rint</code></a>

<h2 id="Matrix_Math_Functions">Matrix Math Functions</h2>

TensorFlow provides several operations that you can use to add linear algebra
functions on matrices to your graph.

*   <a href="../../api_docs/python/tf/linalg/tensor_diag.md"><code>tf.diag</code></a>
*   <a href="../../api_docs/python/tf/linalg/tensor_diag_part.md"><code>tf.diag_part</code></a>
*   <a href="../../api_docs/python/tf/trace.md"><code>tf.trace</code></a>
*   <a href="../../api_docs/python/tf/transpose.md"><code>tf.transpose</code></a>
*   <a href="../../api_docs/python/tf/eye.md"><code>tf.eye</code></a>
*   <a href="../../api_docs/python/tf/linalg/diag.md"><code>tf.matrix_diag</code></a>
*   <a href="../../api_docs/python/tf/linalg/diag_part.md"><code>tf.matrix_diag_part</code></a>
*   <a href="../../api_docs/python/tf/linalg/band_part.md"><code>tf.matrix_band_part</code></a>
*   <a href="../../api_docs/python/tf/linalg/set_diag.md"><code>tf.matrix_set_diag</code></a>
*   <a href="../../api_docs/python/tf/matrix_transpose.md"><code>tf.matrix_transpose</code></a>
*   <a href="../../api_docs/python/tf/matmul.md"><code>tf.matmul</code></a>
*   <a href="../../api_docs/python/tf/norm.md"><code>tf.norm</code></a>
*   <a href="../../api_docs/python/tf/linalg/det.md"><code>tf.matrix_determinant</code></a>
*   <a href="../../api_docs/python/tf/linalg/inv.md"><code>tf.matrix_inverse</code></a>
*   <a href="../../api_docs/python/tf/linalg/cholesky.md"><code>tf.cholesky</code></a>
*   <a href="../../api_docs/python/tf/cholesky_solve.md"><code>tf.cholesky_solve</code></a>
*   <a href="../../api_docs/python/tf/linalg/solve.md"><code>tf.matrix_solve</code></a>
*   <a href="../../api_docs/python/tf/linalg/triangular_solve.md"><code>tf.matrix_triangular_solve</code></a>
*   <a href="../../api_docs/python/tf/matrix_solve_ls.md"><code>tf.matrix_solve_ls</code></a>
*   <a href="../../api_docs/python/tf/linalg/qr.md"><code>tf.qr</code></a>
*   <a href="../../api_docs/python/tf/self_adjoint_eig.md"><code>tf.self_adjoint_eig</code></a>
*   <a href="../../api_docs/python/tf/self_adjoint_eigvals.md"><code>tf.self_adjoint_eigvals</code></a>
*   <a href="../../api_docs/python/tf/svd.md"><code>tf.svd</code></a>


<h2 id="Tensor_Math_Function">Tensor Math Function</h2>

TensorFlow provides operations that you can use to add tensor functions to your
graph.

*   <a href="../../api_docs/python/tf/tensordot.md"><code>tf.tensordot</code></a>


<h2 id="Complex_Number_Functions">Complex Number Functions</h2>

TensorFlow provides several operations that you can use to add complex number
functions to your graph.

*   <a href="../../api_docs/python/tf/complex.md"><code>tf.complex</code></a>
*   <a href="../../api_docs/python/tf/conj.md"><code>tf.conj</code></a>
*   <a href="../../api_docs/python/tf/imag.md"><code>tf.imag</code></a>
*   <a href="../../api_docs/python/tf/angle.md"><code>tf.angle</code></a>
*   <a href="../../api_docs/python/tf/real.md"><code>tf.real</code></a>


<h2 id="Reduction">Reduction</h2>

TensorFlow provides several operations that you can use to perform
common math computations that reduce various dimensions of a tensor.

*   <a href="../../api_docs/python/tf/reduce_sum.md"><code>tf.reduce_sum</code></a>
*   <a href="../../api_docs/python/tf/reduce_prod.md"><code>tf.reduce_prod</code></a>
*   <a href="../../api_docs/python/tf/reduce_min.md"><code>tf.reduce_min</code></a>
*   <a href="../../api_docs/python/tf/reduce_max.md"><code>tf.reduce_max</code></a>
*   <a href="../../api_docs/python/tf/reduce_mean.md"><code>tf.reduce_mean</code></a>
*   <a href="../../api_docs/python/tf/reduce_all.md"><code>tf.reduce_all</code></a>
*   <a href="../../api_docs/python/tf/reduce_any.md"><code>tf.reduce_any</code></a>
*   <a href="../../api_docs/python/tf/reduce_logsumexp.md"><code>tf.reduce_logsumexp</code></a>
*   <a href="../../api_docs/python/tf/count_nonzero.md"><code>tf.count_nonzero</code></a>
*   <a href="../../api_docs/python/tf/accumulate_n.md"><code>tf.accumulate_n</code></a>
*   <a href="../../api_docs/python/tf/einsum.md"><code>tf.einsum</code></a>

<h2 id="Scan">Scan</h2>

TensorFlow provides several operations that you can use to perform scans
(running totals) across one axis of a tensor.

*   <a href="../../api_docs/python/tf/cumsum.md"><code>tf.cumsum</code></a>
*   <a href="../../api_docs/python/tf/cumprod.md"><code>tf.cumprod</code></a>

<h2 id="Segmentation">Segmentation</h2>

TensorFlow provides several operations that you can use to perform common
math computations on tensor segments.
Here a segmentation is a partitioning of a tensor along
the first dimension, i.e. it  defines a mapping from the first dimension onto
`segment_ids`. The `segment_ids` tensor should be the size of
the first dimension, `d0`, with consecutive IDs in the range `0` to `k`,
where `k<d0`.
In particular, a segmentation of a matrix tensor is a mapping of rows to
segments.

For example:

```python
c = tf.constant([[1,2,3,4], [-1,-2,-3,-4], [5,6,7,8]])
tf.segment_sum(c, tf.constant([0, 0, 1]))
  ==>  [[0 0 0 0]
        [5 6 7 8]]
```

*   <a href="../../api_docs/python/tf/math/segment_sum.md"><code>tf.segment_sum</code></a>
*   <a href="../../api_docs/python/tf/math/segment_prod.md"><code>tf.segment_prod</code></a>
*   <a href="../../api_docs/python/tf/math/segment_min.md"><code>tf.segment_min</code></a>
*   <a href="../../api_docs/python/tf/math/segment_max.md"><code>tf.segment_max</code></a>
*   <a href="../../api_docs/python/tf/math/segment_mean.md"><code>tf.segment_mean</code></a>
*   <a href="../../api_docs/python/tf/math/unsorted_segment_sum.md"><code>tf.unsorted_segment_sum</code></a>
*   <a href="../../api_docs/python/tf/sparse_segment_sum.md"><code>tf.sparse_segment_sum</code></a>
*   <a href="../../api_docs/python/tf/sparse_segment_mean.md"><code>tf.sparse_segment_mean</code></a>
*   <a href="../../api_docs/python/tf/sparse_segment_sqrt_n.md"><code>tf.sparse_segment_sqrt_n</code></a>


<h2 id="Sequence_Comparison_and_Indexing">Sequence Comparison and Indexing</h2>

TensorFlow provides several operations that you can use to add sequence
comparison and index extraction to your graph. You can use these operations to
determine sequence differences and determine the indexes of specific values in
a tensor.

*   <a href="../../api_docs/python/tf/argmin.md"><code>tf.argmin</code></a>
*   <a href="../../api_docs/python/tf/argmax.md"><code>tf.argmax</code></a>
*   <a href="../../api_docs/python/tf/setdiff1d.md"><code>tf.setdiff1d</code></a>
*   <a href="../../api_docs/python/tf/where.md"><code>tf.where</code></a>
*   <a href="../../api_docs/python/tf/unique.md"><code>tf.unique</code></a>
*   <a href="../../api_docs/python/tf/edit_distance.md"><code>tf.edit_distance</code></a>
*   <a href="../../api_docs/python/tf/math/invert_permutation.md"><code>tf.invert_permutation</code></a>

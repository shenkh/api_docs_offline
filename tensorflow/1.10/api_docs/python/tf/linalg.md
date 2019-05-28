<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.linalg" />
</div>

# Module: tf.linalg



Defined in [`tensorflow/linalg/__init__.py`](https://www.tensorflow.org/code/tensorflow/linalg/__init__.py).

Operations for linear algebra.

## Classes

[`class LinearOperator`](../tf/linalg/LinearOperator.md): Base class defining a [batch of] linear operator[s].

[`class LinearOperatorBlockDiag`](../tf/linalg/LinearOperatorBlockDiag.md): Combines one or more `LinearOperators` in to a Block Diagonal matrix.

[`class LinearOperatorCirculant`](../tf/linalg/LinearOperatorCirculant.md): `LinearOperator` acting like a circulant matrix.

[`class LinearOperatorCirculant2D`](../tf/linalg/LinearOperatorCirculant2D.md): `LinearOperator` acting like a block circulant matrix.

[`class LinearOperatorCirculant3D`](../tf/linalg/LinearOperatorCirculant3D.md): `LinearOperator` acting like a nested block circulant matrix.

[`class LinearOperatorComposition`](../tf/linalg/LinearOperatorComposition.md): Composes one or more `LinearOperators`.

[`class LinearOperatorDiag`](../tf/linalg/LinearOperatorDiag.md): `LinearOperator` acting like a [batch] square diagonal matrix.

[`class LinearOperatorFullMatrix`](../tf/linalg/LinearOperatorFullMatrix.md): `LinearOperator` that wraps a [batch] matrix.

[`class LinearOperatorIdentity`](../tf/linalg/LinearOperatorIdentity.md): `LinearOperator` acting like a [batch] square identity matrix.

[`class LinearOperatorKronecker`](../tf/linalg/LinearOperatorKronecker.md): Kronecker product between two `LinearOperators`.

[`class LinearOperatorLowRankUpdate`](../tf/linalg/LinearOperatorLowRankUpdate.md): Perturb a `LinearOperator` with a rank `K` update.

[`class LinearOperatorLowerTriangular`](../tf/linalg/LinearOperatorLowerTriangular.md): `LinearOperator` acting like a [batch] square lower triangular matrix.

[`class LinearOperatorScaledIdentity`](../tf/linalg/LinearOperatorScaledIdentity.md): `LinearOperator` acting like a scaled [batch] identity matrix `A = c I`.

## Functions

[`adjoint(...)`](../tf/linalg/adjoint.md): Transposes the last two dimensions of and conjugates tensor `matrix`.

[`band_part(...)`](../tf/matrix_band_part.md): Copy a tensor setting everything outside a central band in each innermost matrix

[`cholesky(...)`](../tf/cholesky.md): Computes the Cholesky decomposition of one or more square matrices.

[`cholesky_solve(...)`](../tf/cholesky_solve.md): Solves systems of linear eqns `A X = RHS`, given Cholesky factorizations.

[`cross(...)`](../tf/cross.md): Compute the pairwise cross product.

[`det(...)`](../tf/matrix_determinant.md): Computes the determinant of one or more square matrices.

[`diag(...)`](../tf/matrix_diag.md): Returns a batched diagonal tensor with a given batched diagonal values.

[`diag_part(...)`](../tf/matrix_diag_part.md): Returns the batched diagonal part of a batched tensor.

[`eigh(...)`](../tf/self_adjoint_eig.md): Computes the eigen decomposition of a batch of self-adjoint matrices.

[`eigvalsh(...)`](../tf/self_adjoint_eigvals.md): Computes the eigenvalues of one or more self-adjoint matrices.

[`einsum(...)`](../tf/einsum.md): A generalized contraction between tensors of arbitrary dimension.

[`expm(...)`](../tf/linalg/expm.md): Computes the matrix exponential of one or more square matrices:

[`eye(...)`](../tf/eye.md): Construct an identity matrix, or a batch of matrices.

[`inv(...)`](../tf/matrix_inverse.md): Computes the inverse of one or more square invertible matrices or their

[`logdet(...)`](../tf/linalg/logdet.md): Computes log of the determinant of a hermitian positive definite matrix.

[`logm(...)`](../tf/linalg/logm.md): Computes the matrix logarithm of one or more square matrices:

[`lstsq(...)`](../tf/matrix_solve_ls.md): Solves one or more linear least-squares problems.

[`norm(...)`](../tf/norm.md): Computes the norm of vectors, matrices, and tensors. (deprecated arguments)

[`qr(...)`](../tf/qr.md): Computes the QR decompositions of one or more matrices.

[`set_diag(...)`](../tf/matrix_set_diag.md): Returns a batched matrix tensor with new batched diagonal values.

[`slogdet(...)`](../tf/linalg/slogdet.md): Computes the sign and the log of the absolute value of the determinant of

[`solve(...)`](../tf/matrix_solve.md): Solves systems of linear equations.

[`svd(...)`](../tf/svd.md): Computes the singular value decompositions of one or more matrices.

[`tensor_diag(...)`](../tf/diag.md): Returns a diagonal tensor with a given diagonal values.

[`tensor_diag_part(...)`](../tf/diag_part.md): Returns the diagonal part of the tensor.

[`tensordot(...)`](../tf/tensordot.md): Tensor contraction of a and b along specified axes.

[`trace(...)`](../tf/trace.md): Compute the trace of a tensor `x`.

[`transpose(...)`](../tf/matrix_transpose.md): Transposes last two dimensions of tensor `a`.

[`triangular_solve(...)`](../tf/matrix_triangular_solve.md): Solves systems of linear equations with upper or lower triangular matrices by


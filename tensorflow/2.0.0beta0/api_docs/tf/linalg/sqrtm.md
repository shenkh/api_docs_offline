<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.linalg.sqrtm" />
<meta itemprop="path" content="Stable" />
</div>

# tf.linalg.sqrtm

Computes the matrix square root of one or more square matrices:

### Aliases:

* `tf.compat.v1.linalg.sqrtm`
* `tf.compat.v1.matrix_square_root`
* `tf.compat.v2.linalg.sqrtm`
* `tf.compat.v2.matrix_square_root`
* `tf.linalg.sqrtm`
* `tf.matrix_square_root`

``` python
tf.linalg.sqrtm(
    input,
    name=None
)
```



Defined in generated file: `python/ops/gen_linalg_ops.py`.

<!-- Placeholder for "Used in" -->

matmul(sqrtm(A), sqrtm(A)) = A

The input matrix should be invertible. If the input matrix is real, it should
have no eigenvalues which are real and negative (pairs of complex conjugate
eigenvalues are allowed).

The matrix square root is computed by first reducing the matrix to 
quasi-triangular form with the real Schur decomposition. The square root 
of the quasi-triangular matrix is then computed directly. Details of 
the algorithm can be found in: Nicholas J. Higham, "Computing real 
square roots of a real matrix", Linear Algebra Appl., 1987.

The input is a tensor of shape `[..., M, M]` whose inner-most 2 dimensions
form square matrices. The output is a tensor of the same shape as the input
containing the matrix square root for all input submatrices `[..., :, :]`.

#### Args:


* <b>`input`</b>: A `Tensor`. Must be one of the following types: `float64`, `float32`, `half`, `complex64`, `complex128`.
  Shape is `[..., M, M]`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.linalg.inv" />
<meta itemprop="path" content="Stable" />
</div>

# tf.linalg.inv

### Aliases:

* `tf.linalg.inv`
* `tf.matrix_inverse`

``` python
tf.linalg.inv(
    input,
    adjoint=False,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_linalg_ops.py`.

See the guides: [Math > Matrix Math Functions](../../../../api_guides/python/math_ops.md#Matrix_Math_Functions), [Upgrade to TensorFlow 1.0 > Upgrading your code manually](../../../../api_guides/python/upgrade.md#Upgrading_your_code_manually)

Computes the inverse of one or more square invertible matrices or their

adjoints (conjugate transposes).

The input is a tensor of shape `[..., M, M]` whose inner-most 2 dimensions
form square matrices. The output is a tensor of the same shape as the input
containing the inverse for all input submatrices `[..., :, :]`.

The op uses LU decomposition with partial pivoting to compute the inverses.

If a matrix is not invertible there is no guarantee what the op does. It
may detect the condition and raise an exception or it may simply return a
garbage result.

#### Args:

* <b>`input`</b>: A `Tensor`. Must be one of the following types: `float64`, `float32`, `complex64`, `complex128`.
    Shape is `[..., M, M]`.
* <b>`adjoint`</b>: An optional `bool`. Defaults to `False`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.
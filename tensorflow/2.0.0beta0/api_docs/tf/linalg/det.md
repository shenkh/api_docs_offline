<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.linalg.det" />
<meta itemprop="path" content="Stable" />
</div>

# tf.linalg.det

Computes the determinant of one or more square matrices.

### Aliases:

* `tf.compat.v1.linalg.det`
* `tf.compat.v1.matrix_determinant`
* `tf.compat.v2.linalg.det`
* `tf.linalg.det`

``` python
tf.linalg.det(
    input,
    name=None
)
```



Defined in generated file: `python/ops/gen_linalg_ops.py`.

<!-- Placeholder for "Used in" -->

The input is a tensor of shape `[..., M, M]` whose inner-most 2 dimensions
form square matrices. The output is a tensor containing the determinants
for all input submatrices `[..., :, :]`.

#### Args:


* <b>`input`</b>: A `Tensor`. Must be one of the following types: `half`, `float32`, `float64`, `complex64`, `complex128`.
  Shape is `[..., M, M]`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.

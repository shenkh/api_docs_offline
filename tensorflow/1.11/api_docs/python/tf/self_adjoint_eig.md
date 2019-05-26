<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.self_adjoint_eig" />
<meta itemprop="path" content="Stable" />
</div>

# tf.self_adjoint_eig

### Aliases:

* `tf.linalg.eigh`
* `tf.self_adjoint_eig`

``` python
tf.self_adjoint_eig(
    tensor,
    name=None
)
```



Defined in [`tensorflow/python/ops/linalg_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/linalg_ops.py).

See the guides: [Math > Matrix Math Functions](../../../api_guides/python/math_ops.md#Matrix_Math_Functions), [Upgrade to TensorFlow 1.0 > Upgrading your code manually](../../../api_guides/python/upgrade.md#Upgrading_your_code_manually)

Computes the eigen decomposition of a batch of self-adjoint matrices.

Computes the eigenvalues and eigenvectors of the innermost N-by-N matrices
in `tensor` such that
`tensor[...,:,:] * v[..., :,i] = e[..., i] * v[...,:,i]`, for i=0...N-1.

#### Args:

* <b>`tensor`</b>: `Tensor` of shape `[..., N, N]`. Only the lower triangular part of
    each inner inner matrix is referenced.
* <b>`name`</b>: string, optional name of the operation.


#### Returns:

* <b>`e`</b>: Eigenvalues. Shape is `[..., N]`. Sorted in non-decreasing order.
* <b>`v`</b>: Eigenvectors. Shape is `[..., N, N]`. The columns of the inner most
    matrices contain eigenvectors of the corresponding matrices in `tensor`
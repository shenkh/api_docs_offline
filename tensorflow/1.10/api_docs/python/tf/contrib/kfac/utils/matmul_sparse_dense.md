<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.utils.matmul_sparse_dense" />
</div>

# tf.contrib.kfac.utils.matmul_sparse_dense

``` python
tf.contrib.kfac.utils.matmul_sparse_dense(
    A,
    B,
    name=None,
    transpose_a=False,
    transpose_b=False
)
```



Defined in [`tensorflow/contrib/kfac/python/ops/utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/utils.py).

Computes matmul(A, B) where A is sparse, B is dense.

#### Args:

* <b>`A`</b>: tf.IndexedSlices with dense shape [m, n].
* <b>`B`</b>: tf.Tensor with shape [n, k].
* <b>`name`</b>: str. Name of op.
* <b>`transpose_a`</b>: Bool. If true we transpose A before multiplying it by B.
    (Default: False)
* <b>`transpose_b`</b>: Bool. If true we transpose B before multiplying it by A.
    (Default: False)


#### Returns:

tf.IndexedSlices resulting from matmul(A, B).


#### Raises:

* <b>`ValueError`</b>: If A doesn't represent a matrix.
* <b>`ValueError`</b>: If B is not rank-2.
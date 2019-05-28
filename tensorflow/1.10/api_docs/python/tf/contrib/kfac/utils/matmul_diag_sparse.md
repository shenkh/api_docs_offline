<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.utils.matmul_diag_sparse" />
</div>

# tf.contrib.kfac.utils.matmul_diag_sparse

``` python
tf.contrib.kfac.utils.matmul_diag_sparse(
    A_diag,
    B,
    name=None
)
```



Defined in [`tensorflow/contrib/kfac/python/ops/utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/utils.py).

Computes matmul(A, B) where A is a diagonal matrix, B is sparse.

#### Args:

* <b>`A_diag`</b>: diagonal entries of matrix A of shape [m, m].
* <b>`B`</b>: tf.IndexedSlices. Represents matrix of shape [m, n].
* <b>`name`</b>: str. Name of op.


#### Returns:

tf.IndexedSlices resulting from matmul(A, B).


#### Raises:

* <b>`ValueError`</b>: If A_diag is not rank-1.
* <b>`ValueError`</b>: If B doesn't represent a matrix.
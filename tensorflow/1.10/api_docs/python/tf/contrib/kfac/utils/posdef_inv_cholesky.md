<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.utils.posdef_inv_cholesky" />
</div>

# tf.contrib.kfac.utils.posdef_inv_cholesky

``` python
tf.contrib.kfac.utils.posdef_inv_cholesky(
    tensor,
    identity,
    damping
)
```



Defined in [`tensorflow/contrib/kfac/python/ops/utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/utils.py).

Computes inverse(tensor + damping * identity) with Cholesky.
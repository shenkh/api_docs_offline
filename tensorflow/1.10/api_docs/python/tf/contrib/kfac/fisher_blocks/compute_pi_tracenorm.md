<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.fisher_blocks.compute_pi_tracenorm" />
</div>

# tf.contrib.kfac.fisher_blocks.compute_pi_tracenorm

``` python
tf.contrib.kfac.fisher_blocks.compute_pi_tracenorm(
    left_cov,
    right_cov
)
```



Defined in [`tensorflow/contrib/kfac/python/ops/fisher_blocks.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/fisher_blocks.py).

Computes the scalar constant pi for Tikhonov regularization/damping.

$$\pi = \sqrt{ (trace(A) / dim(A)) / (trace(B) / dim(B)) }$$
See section 6.3 of https://arxiv.org/pdf/1503.05671.pdf for details.

#### Args:

* <b>`left_cov`</b>: A LinearOperator object. The left Kronecker factor "covariance".
* <b>`right_cov`</b>: A LinearOperator object. The right Kronecker factor "covariance".


#### Returns:

The computed scalar constant pi for these Kronecker Factors (as a Tensor).
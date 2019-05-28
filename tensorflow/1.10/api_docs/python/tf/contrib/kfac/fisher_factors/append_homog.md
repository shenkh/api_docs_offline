<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.fisher_factors.append_homog" />
</div>

# tf.contrib.kfac.fisher_factors.append_homog

``` python
tf.contrib.kfac.fisher_factors.append_homog(tensor)
```



Defined in [`tensorflow/contrib/kfac/python/ops/fisher_factors.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/fisher_factors.py).

Appends a homogeneous coordinate to the last dimension of a Tensor.

#### Args:

* <b>`tensor`</b>: A Tensor.


#### Returns:

A Tensor identical to the input but one larger in the last dimension.  The
new entries are filled with ones.
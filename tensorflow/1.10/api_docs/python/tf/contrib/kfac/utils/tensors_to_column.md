<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.utils.tensors_to_column" />
</div>

# tf.contrib.kfac.utils.tensors_to_column

``` python
tf.contrib.kfac.utils.tensors_to_column(tensors)
```



Defined in [`tensorflow/contrib/kfac/python/ops/utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/utils.py).

Converts a tensor or list of tensors to a column vector.

#### Args:

* <b>`tensors`</b>: A tensor or list of tensors.


#### Returns:

The tensors reshaped into vectors and stacked on top of each other.
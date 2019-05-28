<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.is_tensor" />
</div>

# tf.contrib.framework.is_tensor

``` python
tf.contrib.framework.is_tensor(x)
```



Defined in [`tensorflow/python/framework/tensor_util.py`](https://www.tensorflow.org/code/tensorflow/python/framework/tensor_util.py).

See the guide: [Framework (contrib)](../../../../../api_guides/python/contrib.framework.md)

Check whether `x` is of tensor type.

Check whether an object is a tensor. Equivalent to
`isinstance(x, [tf.Tensor, tf.SparseTensor, tf.Variable])`.

#### Args:

* <b>`x`</b>: A python object to check.


#### Returns:

`True` if `x` is a tensor, `False` if not.
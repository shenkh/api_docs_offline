<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.is_tensor" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.framework.is_tensor

``` python
tf.contrib.framework.is_tensor(x)
```



Defined in [`tensorflow/python/framework/tensor_util.py`](/code/stable/tensorflow/python/framework/tensor_util.py).

Check whether `x` is of tensor type.

Check whether an object is a tensor. This check is equivalent to calling
`isinstance(x, (tf.Tensor, tf.SparseTensor, tf.Variable))` and also checks
if all the component variables of a MirroredVariable or a TowerLocalVariable
are tensors.

#### Args:

* <b>`x`</b>: A python object to check.


#### Returns:

`True` if `x` is a tensor, `False` if not.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.is_tensor" />
<meta itemprop="path" content="Stable" />
</div>

# tf.is_tensor

``` python
tf.is_tensor(x)
```



Defined in [`tensorflow/python/framework/tensor_util.py`](/code/stable/tensorflow/python/framework/tensor_util.py).

Checks whether `x` is a tensor or "tensor-like".

If `is_tensor(x)` returns `True`, it is safe to assume that `x` is a tensor or
can be converted to a tensor using `ops.convert_to_tensor(x)`.

#### Args:

* <b>`x`</b>: A python object to check.


#### Returns:

`True` if `x` is a tensor or "tensor-like", `False` if not.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.assert_proper_iterable" />
<meta itemprop="path" content="Stable" />
</div>

# tf.assert_proper_iterable

``` python
tf.assert_proper_iterable(values)
```



Defined in [`tensorflow/python/ops/check_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/check_ops.py).

Static assert that values is a "proper" iterable.

`Ops` that expect iterables of `Tensor` can call this to validate input.
Useful since `Tensor`, `ndarray`, byte/text type are all iterables themselves.

#### Args:

* <b>`values`</b>:  Object to be checked.


#### Raises:

* <b>`TypeError`</b>:  If `values` is not iterable or is one of
    `Tensor`, `SparseTensor`, `np.array`, <a href="../tf/compat/bytes_or_text_types.md"><code>tf.compat.bytes_or_text_types</code></a>.
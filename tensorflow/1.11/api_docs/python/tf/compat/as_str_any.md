<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.as_str_any" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.as_str_any

``` python
tf.compat.as_str_any(value)
```



Defined in [`tensorflow/python/util/compat.py`](https://www.tensorflow.org/code/tensorflow/python/util/compat.py).

Converts to `str` as `str(value)`, but use `as_str` for `bytes`.

#### Args:

* <b>`value`</b>: A object that can be converted to `str`.


#### Returns:

A `str` object.
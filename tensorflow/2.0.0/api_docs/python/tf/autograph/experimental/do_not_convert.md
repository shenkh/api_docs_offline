<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.autograph.experimental.do_not_convert" />
<meta itemprop="path" content="Stable" />
</div>

# tf.autograph.experimental.do_not_convert

``` python
tf.autograph.experimental.do_not_convert(func=None)
```



Defined in [`tensorflow/python/autograph/impl/api.py`](/code/stable/tensorflow/python/autograph/impl/api.py).

Decorator that suppresses the conversion of a function.

#### Args:

* <b>`func`</b>: function to decorate.


#### Returns:

If `func` is not None, returns a `Callable` which is equivalent to
`func`, but is not converted by AutoGraph.
If `func` is None, returns a decorator that, when invoked with a
single `func` argument, returns a `Callable` equivalent to the
above case.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.autograph.experimental.do_not_convert" />
<meta itemprop="path" content="Stable" />
</div>

# tf.autograph.experimental.do_not_convert

Decorator that suppresses the conversion of a function.

### Aliases:

* `tf.autograph.experimental.do_not_convert`
* `tf.compat.v1.autograph.experimental.do_not_convert`
* `tf.compat.v2.autograph.experimental.do_not_convert`

``` python
tf.autograph.experimental.do_not_convert(
    func=None,
    run_as=RunMode.GRAPH,
    return_dtypes=None
)
```



Defined in [`python/autograph/impl/api.py`](/code/stable/tensorflow/python/autograph/impl/api.py).

<!-- Placeholder for "Used in" -->

See also: docs/pyfunc_dtypes.md

#### Args:


* <b>`func`</b>: function to decorate.
* <b>`run_as`</b>: RunMode, specifies how to use the function in TensorFlow.
* <b>`return_dtypes`</b>: Optional[Iterable[ Union[tf.DType,
  utils.py_func.MatchDType]]], the return data types of the converted
  function, if run_as is RunMode.PY_FUNC. Ignored otherwise. May be set to
  None if the function has no return values.


#### Returns:

If `func` is not None, returns a `Callable` which is equivalent to
`func`, but is not converted by AutoGraph.
If `func` is None, returns a decorator that, when invoked with a
single `func` argument, returns a `Callable` equivalent to the
above case.

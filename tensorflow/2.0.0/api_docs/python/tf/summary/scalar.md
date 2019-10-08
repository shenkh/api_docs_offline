<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.scalar" />
<meta itemprop="path" content="Stable" />
</div>

# tf.summary.scalar

``` python
tf.summary.scalar(
    name,
    data,
    step=None,
    description=None
)
```

Write a scalar summary.

#### Arguments:

* <b>`name`</b>: A name for this summary. The summary tag used for TensorBoard will
    be this name prefixed by any active name scopes.
* <b>`data`</b>: A real numeric scalar value, convertible to a `float32` Tensor.
* <b>`step`</b>: Explicit `int64`-castable monotonic step value for this summary. If
    omitted, this defaults to `tf.summary.experimental.get_step()`, which must
    not be None.
* <b>`description`</b>: Optional long-form description for this summary, as a
    constant `str`. Markdown is supported. Defaults to empty.


#### Returns:

True on success, or false if no summary was written because no default
summary writer was available.


#### Raises:

* <b>`ValueError`</b>: if a default writer exists, but no step was provided and
    `tf.summary.experimental.get_step()` is None.
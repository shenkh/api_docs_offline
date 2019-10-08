<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.lite.experimental.load_delegate" />
<meta itemprop="path" content="Stable" />
</div>

# tf.lite.experimental.load_delegate

``` python
tf.lite.experimental.load_delegate(
    library,
    options=None
)
```



Defined in [`tensorflow/lite/python/interpreter.py`](/code/stable/tensorflow/lite/python/interpreter.py).

Returns loaded Delegate object.

#### Args:

* <b>`library`</b>: Name of shared library containing the
    [TfLiteDelegate](https://www.tensorflow.org/lite/performance/delegates).
* <b>`options`</b>: Dictionary of options that are required to load the delegate. All
    keys and values in the dictionary should be convertible to str. Consult
    the documentation of the specific delegate for required and legal options.
    (default None)


#### Returns:

Delegate object.


#### Raises:

* <b>`ValueError`</b>: Delegate failed to load.
* <b>`RuntimeError`</b>: If delegate loading is used on unsupported platform.
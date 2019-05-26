<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.autograph.convert" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.autograph.convert

``` python
tf.contrib.autograph.convert(
    recursive=False,
    verbose=False
)
```



Defined in [`tensorflow/python/autograph/impl/api.py`](/code/stable/tensorflow/python/autograph/impl/api.py).

Decorator that compiles a function to use TensorFlow ops.

The decorator is dynamic - it recompiles the target whenever the decorated
function is called. This means the parameter values are known at conversion.
It also means that repeated calls with different types of parameters will be
correctly processed.

#### Args:

* <b>`recursive`</b>: bool, whether to recursively convert any functions or classes
      that the converted function may use.
* <b>`verbose`</b>: bool, whether to output the compiled code in the logs.


#### Returns:

Callable, a decorator that converts the given function into an equivalent
function that uses TensorFlow ops.
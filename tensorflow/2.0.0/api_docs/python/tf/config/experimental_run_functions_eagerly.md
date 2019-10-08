<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental_run_functions_eagerly" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental_run_functions_eagerly

``` python
tf.config.experimental_run_functions_eagerly(run_eagerly)
```



Defined in [`tensorflow/python/eager/def_function.py`](/code/stable/tensorflow/python/eager/def_function.py).

Enables / disables eager execution of <a href="../../tf/function.md"><code>tf.function</code></a>s.

After calling `tf.config.experimental_run_functions_eagerly(True)` all
invocations of tf.function will run eagerly instead of running through a graph
function.

This can be useful for debugging or profiling.

Similarly, calling `tf.config.experimental_run_functions_eagerly(False)` will
revert the behavior of all functions to graph functions.

#### Args:

* <b>`run_eagerly`</b>: Boolean. Whether to run functions eagerly.
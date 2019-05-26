<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.reset_default_graph" />
<meta itemprop="path" content="Stable" />
</div>

# tf.reset_default_graph

``` python
tf.reset_default_graph()
```



Defined in [`tensorflow/python/framework/ops.py`](https://www.tensorflow.org/code/tensorflow/python/framework/ops.py).

Clears the default graph stack and resets the global default graph.

NOTE: The default graph is a property of the current thread. This
function applies only to the current thread.  Calling this function while
a <a href="../tf/Session.md"><code>tf.Session</code></a> or <a href="../tf/InteractiveSession.md"><code>tf.InteractiveSession</code></a> is active will result in undefined
behavior. Using any previously created <a href="../tf/Operation.md"><code>tf.Operation</code></a> or <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> objects
after calling this function will result in undefined behavior.
#### Raises:

* <b>`AssertionError`</b>: If this function is called within a nested graph.
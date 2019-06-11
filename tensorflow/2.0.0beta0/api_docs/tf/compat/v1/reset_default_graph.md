<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.reset_default_graph" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.reset_default_graph

Clears the default graph stack and resets the global default graph.

``` python
tf.compat.v1.reset_default_graph()
```



Defined in [`python/framework/ops.py`](/code/stable/tensorflow/python/framework/ops.py).

<!-- Placeholder for "Used in" -->

NOTE: The default graph is a property of the current thread. This
function applies only to the current thread.  Calling this function while
a <a href="../../../tf/compat/v1/Session.md"><code>tf.compat.v1.Session</code></a> or <a href="../../../tf/compat/v1/InteractiveSession.md"><code>tf.compat.v1.InteractiveSession</code></a> is active will
result in undefined
behavior. Using any previously created <a href="../../../tf/Operation.md"><code>tf.Operation</code></a> or <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> objects
after calling this function will result in undefined behavior.
Raises:
  AssertionError: If this function is called within a nested graph.
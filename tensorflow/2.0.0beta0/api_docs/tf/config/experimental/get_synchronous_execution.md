<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental.get_synchronous_execution" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental.get_synchronous_execution

Gets whether operations are executed synchronously or asynchronously.

### Aliases:

* `tf.compat.v1.config.experimental.get_synchronous_execution`
* `tf.compat.v2.config.experimental.get_synchronous_execution`
* `tf.config.experimental.get_synchronous_execution`

``` python
tf.config.experimental.get_synchronous_execution()
```



Defined in [`python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

<!-- Placeholder for "Used in" -->

TensorFlow can execute operations synchronously or asynchronously. If
asynchronous execution is enabled, operations may return "non-ready" handles.

#### Returns:

Current thread execution mode

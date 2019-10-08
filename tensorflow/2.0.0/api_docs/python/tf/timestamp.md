<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.timestamp" />
<meta itemprop="path" content="Stable" />
</div>

# tf.timestamp

``` python
tf.timestamp(name=None)
```



Defined in generated file: `tensorflow/python/ops/gen_logging_ops.py`.

Provides the time since epoch in seconds.

Returns the timestamp as a `float64` for seconds since the Unix epoch.

Note: the timestamp is computed when the op is executed, not when it is added
to the graph.

#### Args:

* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `float64`.
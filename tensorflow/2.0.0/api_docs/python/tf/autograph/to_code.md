<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.autograph.to_code" />
<meta itemprop="path" content="Stable" />
</div>

# tf.autograph.to_code

``` python
tf.autograph.to_code(
    entity,
    recursive=True,
    experimental_optional_features=None
)
```



Defined in [`tensorflow/python/autograph/impl/api.py`](/code/stable/tensorflow/python/autograph/impl/api.py).

Similar to `to_graph`, but returns Python source code as a string.

Also see: <a href="../../tf/autograph/to_graph.md"><code>tf.autograph.to_graph</code></a>.

`to_graph` returns the Python source code that can be used to generate a
TensorFlow graph that is functionally identical to the input Python code.

#### Args:

* <b>`entity`</b>: Python callable or class to convert.
* <b>`recursive`</b>: Whether to recursively convert any functions that the converted
    function may call.
* <b>`experimental_optional_features`</b>: `None`, a tuple of, or a single
    <a href="../../tf/autograph/experimental/Feature.md"><code>tf.autograph.experimental.Feature</code></a> value. Controls the use of optional
    features in the conversion process.


#### Returns:

The converted code as string.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.autograph.to_graph" />
<meta itemprop="path" content="Stable" />
</div>

# tf.autograph.to_graph

``` python
tf.autograph.to_graph(
    entity,
    recursive=True,
    experimental_optional_features=None
)
```



Defined in [`tensorflow/python/autograph/impl/api.py`](/code/stable/tensorflow/python/autograph/impl/api.py).

Converts a Python entity into a TensorFlow graph.

Also see: <a href="../../tf/autograph/to_code.md"><code>tf.autograph.to_code</code></a>, <a href="../../tf/function.md"><code>tf.function</code></a>.

Unlike <a href="../../tf/function.md"><code>tf.function</code></a>, `to_graph` is a low-level transpiler that converts
Python code to TensorFlow graph code. It does not implement any caching,
variable management or create any actual ops, and is best used where greater
control over the generated TensorFlow graph is desired. Another difference
from <a href="../../tf/function.md"><code>tf.function</code></a> is that `to_graph` will not wrap the graph into a
TensorFlow function or a Python callable. Internally, <a href="../../tf/function.md"><code>tf.function</code></a> uses
`to_graph`.

_Example Usage_

```python
  def foo(x):
    if x > 0:
      y = x * x
    else:
      y = -x
    return y

  converted_foo = to_graph(foo)

  x = tf.constant(1)
  y = converted_foo(x)  # converted_foo is a TensorFlow Op-like.
  assert is_tensor(y)
```

Supported Python entities include:
  * functions
  * classes
  * object methods

Functions are converted into new functions with converted code.

Classes are converted by generating a new class whose methods use converted
code.

Methods are converted into unbound function that have an additional first
argument called `self`.

#### Args:

* <b>`entity`</b>: Python callable or class to convert.
* <b>`recursive`</b>: Whether to recursively convert any functions that the converted
    function may call.
* <b>`experimental_optional_features`</b>: `None`, a tuple of, or a single
    <a href="../../tf/autograph/experimental/Feature.md"><code>tf.autograph.experimental.Feature</code></a> value. Controls the use of optional
    features in the conversion process.


#### Returns:

Same as `entity`, the converted Python function or class.


#### Raises:

* <b>`ValueError`</b>: If the entity could not be converted.
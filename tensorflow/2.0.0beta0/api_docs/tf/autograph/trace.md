<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.autograph.trace" />
<meta itemprop="path" content="Stable" />
</div>

# tf.autograph.trace

Traces argument information at compilation time.

### Aliases:

* `tf.autograph.trace`
* `tf.compat.v1.autograph.trace`
* `tf.compat.v2.autograph.trace`

``` python
tf.autograph.trace(*args)
```



Defined in [`python/autograph/utils/ag_logging.py`](/code/stable/tensorflow/python/autograph/utils/ag_logging.py).

<!-- Placeholder for "Used in" -->

`trace` is useful when debugging, and it always executes during the tracing
phase, that is, when the TF graph is constructed.

_Example usage_

```python
import tensorflow as tf

for i in tf.range(10):
  tf.autograph.trace(i)
# Output: <Tensor ...>
```

#### Args:


* <b>`*args`</b>: Arguments to print to `sys.stdout`.
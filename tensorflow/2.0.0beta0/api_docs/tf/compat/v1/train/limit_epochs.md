<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.train.limit_epochs" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.train.limit_epochs

Returns tensor `num_epochs` times and then raises an `OutOfRange` error. (deprecated)

``` python
tf.compat.v1.train.limit_epochs(
    tensor,
    num_epochs=None,
    name=None
)
```



Defined in [`python/training/input.py`](/code/stable/tensorflow/python/training/input.py).

<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Queue-based input pipelines have been replaced by <a href="../../../../tf/data.md"><code>tf.data</code></a>. Use `tf.data.Dataset.from_tensors(tensor).repeat(num_epochs)`.

Note: creates local counter `epochs`. Use `local_variables_initializer()` to
initialize local variables.

#### Args:


* <b>`tensor`</b>: Any `Tensor`.
* <b>`num_epochs`</b>: A positive integer (optional).  If specified, limits the number
  of steps the output tensor may be evaluated.
* <b>`name`</b>: A name for the operations (optional).


#### Returns:

tensor or `OutOfRange`.



#### Raises:


* <b>`ValueError`</b>: if `num_epochs` is invalid.
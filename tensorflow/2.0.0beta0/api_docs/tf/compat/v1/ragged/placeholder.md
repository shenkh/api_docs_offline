<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.ragged.placeholder" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.ragged.placeholder

Creates a placeholder for a <a href="../../../../tf/RaggedTensor.md"><code>tf.RaggedTensor</code></a> that will always be fed.

``` python
tf.compat.v1.ragged.placeholder(
    dtype,
    ragged_rank,
    value_shape=None,
    name=None
)
```



Defined in [`python/ops/ragged/ragged_factory_ops.py`](/code/stable/tensorflow/python/ops/ragged/ragged_factory_ops.py).

<!-- Placeholder for "Used in" -->

**Important**: This ragged tensor will produce an error if evaluated.
Its value must be fed using the `feed_dict` optional argument to
`Session.run()`, `Tensor.eval()`, or `Operation.run()`.

@compatibility{eager} Placeholders are not compatible with eager execution.

#### Args:


* <b>`dtype`</b>: The data type for the `RaggedTensor`.
* <b>`ragged_rank`</b>: The ragged rank for the `RaggedTensor`
* <b>`value_shape`</b>: The shape for individual flat values in the `RaggedTensor`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `RaggedTensor` that may be used as a handle for feeding a value, but
not evaluated directly.



#### Raises:


* <b>`RuntimeError`</b>: if eager execution is enabled
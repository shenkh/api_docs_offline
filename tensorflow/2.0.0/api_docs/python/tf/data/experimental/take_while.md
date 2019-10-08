<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.take_while" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.take_while

``` python
tf.data.experimental.take_while(predicate)
```



Defined in [`tensorflow/python/data/experimental/ops/take_while_ops.py`](/code/stable/tensorflow/python/data/experimental/ops/take_while_ops.py).

A transformation that stops dataset iteration based on a `predicate`.

#### Args:

* <b>`predicate`</b>: A function that maps a nested structure of tensors (having shapes
    and types defined by `self.output_shapes` and `self.output_types`) to a
    scalar <a href="../../../tf/dtypes.md#bool"><code>tf.bool</code></a> tensor.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.
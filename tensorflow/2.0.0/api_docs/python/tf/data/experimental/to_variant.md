<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.to_variant" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.to_variant

``` python
tf.data.experimental.to_variant(dataset)
```



Defined in [`tensorflow/python/data/ops/dataset_ops.py`](/code/stable/tensorflow/python/data/ops/dataset_ops.py).

Returns a variant representing the given dataset.

#### Args:

* <b>`dataset`</b>: A <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a>.


#### Returns:

A scalar <a href="../../../tf/dtypes.md#variant"><code>tf.variant</code></a> tensor representing the given dataset.
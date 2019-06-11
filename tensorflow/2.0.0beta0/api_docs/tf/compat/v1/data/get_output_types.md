<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.data.get_output_types" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.data.get_output_types

Returns the output shapes of a `Dataset` or `Iterator`.

``` python
tf.compat.v1.data.get_output_types(dataset_or_iterator)
```



Defined in [`python/data/ops/dataset_ops.py`](/code/stable/tensorflow/python/data/ops/dataset_ops.py).

<!-- Placeholder for "Used in" -->

This utility method replaces the deprecated-in-V2
`tf.compat.v1.Dataset.output_types` property.

#### Args:


* <b>`dataset_or_iterator`</b>: A <a href="../../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a>, <a href="../../../../tf/compat/v1/data/Iterator.md"><code>tf.compat.v1.data.Iterator</code></a>, or
  `IteratorV2`.


#### Returns:

A nested structure of <a href="../../../../tf/dtypes/DType.md"><code>tf.DType</code></a> objects corresponding to each component
of an element of this dataset.

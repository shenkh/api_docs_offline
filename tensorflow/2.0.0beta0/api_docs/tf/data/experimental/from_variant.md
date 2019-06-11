<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.from_variant" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.from_variant

Constructs a dataset from the given variant and structure.

### Aliases:

* `tf.compat.v1.data.experimental.from_variant`
* `tf.compat.v2.data.experimental.from_variant`
* `tf.data.experimental.from_variant`

``` python
tf.data.experimental.from_variant(
    variant,
    structure
)
```



Defined in [`python/data/ops/dataset_ops.py`](/code/stable/tensorflow/python/data/ops/dataset_ops.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`variant`</b>: A scalar <a href="../../../tf.md#variant"><code>tf.variant</code></a> tensor representing a dataset.
* <b>`structure`</b>: A <a href="../../../tf/data/experimental/Structure.md"><code>tf.data.experimental.Structure</code></a> object representing the
  structure of each element in the dataset.


#### Returns:

A <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> instance.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.from_variant" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.from_variant

``` python
tf.data.experimental.from_variant(
    variant,
    structure
)
```



Defined in [`tensorflow/python/data/ops/dataset_ops.py`](/code/stable/tensorflow/python/data/ops/dataset_ops.py).

Constructs a dataset from the given variant and structure.

#### Args:

* <b>`variant`</b>: A scalar <a href="../../../tf/dtypes.md#variant"><code>tf.variant</code></a> tensor representing a dataset.
* <b>`structure`</b>: A `tf.data.experimental.Structure` object representing the
    structure of each element in the dataset.


#### Returns:

A <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> instance.
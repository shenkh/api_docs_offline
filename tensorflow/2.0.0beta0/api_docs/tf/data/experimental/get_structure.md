<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.get_structure" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.get_structure

Returns the <a href="../../../tf/data/experimental/Structure.md"><code>tf.data.experimental.Structure</code></a> of a `Dataset` or `Iterator`.

### Aliases:

* `tf.compat.v1.data.experimental.get_structure`
* `tf.compat.v2.data.experimental.get_structure`
* `tf.data.experimental.get_structure`

``` python
tf.data.experimental.get_structure(dataset_or_iterator)
```



Defined in [`python/data/ops/dataset_ops.py`](/code/stable/tensorflow/python/data/ops/dataset_ops.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`dataset_or_iterator`</b>: A <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a>, <a href="../../../tf/compat/v1/data/Iterator.md"><code>tf.compat.v1.data.Iterator</code></a>, or
  `IteratorV2`.


#### Returns:

A <a href="../../../tf/data/experimental/Structure.md"><code>tf.data.experimental.Structure</code></a> representing the structure of the
elements of `dataset_or_iterator`.



#### Raises:


* <b>`TypeError`</b>: If `dataset_or_iterator` is not a dataset or iterator object.
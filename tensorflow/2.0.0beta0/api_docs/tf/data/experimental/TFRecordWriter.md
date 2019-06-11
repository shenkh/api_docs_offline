<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.TFRecordWriter" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="write"/>
</div>

# tf.data.experimental.TFRecordWriter

## Class `TFRecordWriter`

Writes data to a TFRecord file.



### Aliases:

* Class `tf.compat.v1.data.experimental.TFRecordWriter`
* Class `tf.compat.v2.data.experimental.TFRecordWriter`
* Class `tf.data.experimental.TFRecordWriter`



Defined in [`python/data/experimental/ops/writers.py`](/code/stable/tensorflow/python/data/experimental/ops/writers.py).

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    filename,
    compression_type=None
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="write"><code>write</code></h3>

``` python
write(dataset)
```

Returns a <a href="../../../tf/Operation.md"><code>tf.Operation</code></a> to write a dataset to a file.


#### Args:


* <b>`dataset`</b>: a <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> whose elements are to be written to a file


#### Returns:

A <a href="../../../tf/Operation.md"><code>tf.Operation</code></a> that, when run, writes contents of `dataset` to a file.





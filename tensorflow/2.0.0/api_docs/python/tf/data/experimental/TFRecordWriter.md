<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.TFRecordWriter" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="write"/>
</div>

# tf.data.experimental.TFRecordWriter

## Class `TFRecordWriter`





Defined in [`tensorflow/python/data/experimental/ops/writers.py`](/code/stable/tensorflow/python/data/experimental/ops/writers.py).

Writes data to a TFRecord file.

To write a `dataset` to a single TFRecord file:

```python
dataset = ... # dataset to be written
writer = tf.data.experimental.TFRecordWriter(PATH)
writer.write(dataset)
```

To shard a `dataset` across multiple TFRecord files:

```python
dataset = ... # dataset to be written

def reduce_func(key, dataset):
  filename = tf.strings.join([PATH_PREFIX, tf.strings.as_string(key)])
  writer = tf.data.experimental.TFRecordWriter(filename)
  writer.write(dataset.map(lambda _, x: x))
  return tf.data.Dataset.from_tensors(filename)

dataset = dataset.enumerate()
dataset = dataset.apply(tf.data.experimental.group_by_window(
  lambda i, _: i % NUM_SHARDS, reduce_func, tf.int64.max
))
```

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




<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.cardinality" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.cardinality

``` python
tf.data.experimental.cardinality(dataset)
```



Defined in [`tensorflow/python/data/experimental/ops/cardinality.py`](/code/stable/tensorflow/python/data/experimental/ops/cardinality.py).

Returns the cardinality of `dataset`, if known.

The operation returns the cardinality of `dataset`. The operation may return
<a href="../../../tf/data/experimental.md#INFINITE_CARDINALITY"><code>tf.data.experimental.INFINITE_CARDINALITY</code></a> if `dataset` contains an infinite
number of elements or <a href="../../../tf/data/experimental.md#UNKNOWN_CARDINALITY"><code>tf.data.experimental.UNKNOWN_CARDINALITY</code></a> if the
analysis fails to determine the number of elements in `dataset` (e.g. when the
dataset source is a file).

#### Args:

* <b>`dataset`</b>: A <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> for which to determine cardinality.


#### Returns:

A scalar <a href="../../../tf/dtypes.md#int64"><code>tf.int64</code></a> `Tensor` representing the cardinality of `dataset`. If
the cardinality is infinite or unknown, the operation returns the named
constant `INFINITE_CARDINALITY` and `UNKNOWN_CARDINALITY` respectively.
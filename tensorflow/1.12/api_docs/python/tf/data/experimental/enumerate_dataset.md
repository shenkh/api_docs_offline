<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.enumerate_dataset" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.enumerate_dataset

``` python
tf.data.experimental.enumerate_dataset(start=0)
```



Defined in [`tensorflow/python/data/experimental/ops/enumerate_ops.py`](/code/stable/tensorflow/python/data/experimental/ops/enumerate_ops.py).

A transformation that enumerate the elements of a dataset.

It is Similar to python's `enumerate`.
For example:

```python
# NOTE: The following examples use `{ ... }` to represent the
# contents of a dataset.
a = { 1, 2, 3 }
b = { (7, 8), (9, 10) }

# The nested structure of the `datasets` argument determines the
# structure of elements in the resulting dataset.
a.apply(tf.data.experimental.enumerate(start=5)) == { (5, 1), (6, 2), (7, 3) }
b.apply(tf.data.experimental.enumerate()) == { (0, (7, 8)), (1, (9, 10)) }
```

#### Args:

* <b>`start`</b>: A <a href="../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the start
    value for enumeration.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.
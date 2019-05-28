<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.enumerate_dataset" />
</div>

# tf.contrib.data.enumerate_dataset

``` python
tf.contrib.data.enumerate_dataset(start=0)
```



Defined in [`tensorflow/contrib/data/python/ops/enumerate_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/data/python/ops/enumerate_ops.py).

See the guide: [Dataset Input Pipeline > Transformations on existing datasets](../../../../../api_guides/python/input_dataset.md#Transformations_on_existing_datasets)

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
a.apply(tf.contrib.data.enumerate(start=5)) == { (5, 1), (6, 2), (7, 3) }
b.apply(tf.contrib.data.enumerate()) == { (0, (7, 8)), (1, (9, 10)) }
```

#### Args:

* <b>`start`</b>: A <a href="../../../tf/int64.md"><code>tf.int64</code></a> scalar <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the start
    value for enumeration.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.
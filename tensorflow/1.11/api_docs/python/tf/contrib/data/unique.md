<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.unique" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.data.unique

``` python
tf.contrib.data.unique()
```



Defined in [`tensorflow/contrib/data/python/ops/unique.py`](https://www.tensorflow.org/code/tensorflow/contrib/data/python/ops/unique.py).

Creates a `Dataset` from another `Dataset`, discarding duplicates.

Use this transformation to produce a dataset that contains one instance of
each unique element in the input. For example:

```python
dataset = tf.data.Dataset.from_tensor_slices([1, 37, 2, 37, 2, 1])

# Using `unique()` will drop the duplicate elements.
dataset = dataset.apply(tf.contrib.data.unique())  # ==> { 1, 37, 2 }
```

#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.
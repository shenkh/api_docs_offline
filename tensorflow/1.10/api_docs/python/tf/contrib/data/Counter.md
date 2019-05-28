<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.Counter" />
</div>

# tf.contrib.data.Counter

``` python
tf.contrib.data.Counter(
    start=0,
    step=1,
    dtype=tf.int64
)
```



Defined in [`tensorflow/contrib/data/python/ops/counter.py`](https://www.tensorflow.org/code/tensorflow/contrib/data/python/ops/counter.py).

Creates a `Dataset` that counts from `start` in steps of size `step`.

For example:

```python
Dataset.count() == [0, 1, 2, ...)
Dataset.count(2) == [2, 3, ...)
Dataset.count(2, 5) == [2, 7, 12, ...)
Dataset.count(0, -1) == [0, -1, -2, ...)
Dataset.count(10, -1) == [10, 9, ...)
```

#### Args:

* <b>`start`</b>: (Optional.) The starting value for the counter. Defaults to 0.
* <b>`step`</b>: (Optional.) The step size for the counter. Defaults to 1.
* <b>`dtype`</b>: (Optional.) The data type for counter elements. Defaults to
    <a href="../../../tf/int64.md"><code>tf.int64</code></a>.


#### Returns:

A `Dataset` of scalar `dtype` elements.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.shuffle_and_repeat" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.shuffle_and_repeat

``` python
tf.data.experimental.shuffle_and_repeat(
    buffer_size,
    count=None,
    seed=None
)
```



Defined in [`tensorflow/python/data/experimental/ops/shuffle_ops.py`](/code/stable/tensorflow/python/data/experimental/ops/shuffle_ops.py).

Shuffles and repeats a Dataset returning a new permutation for each epoch. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.data.Dataset.shuffle(buffer_size, seed)` followed by `tf.data.Dataset.repeat(count)`. Static tf.data optimizations will take care of using the fused implementation.

`dataset.apply(tf.data.experimental.shuffle_and_repeat(buffer_size, count))`

is equivalent to

`dataset.shuffle(buffer_size, reshuffle_each_iteration=True).repeat(count)`

The difference is that the latter dataset is not serializable. So,
if you need to checkpoint an input pipeline with reshuffling you must use
this implementation.

#### Args:

* <b>`buffer_size`</b>: A <a href="../../../tf/dtypes.md#int64"><code>tf.int64</code></a> scalar <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the
    maximum number elements that will be buffered when prefetching.
* <b>`count`</b>: (Optional.) A <a href="../../../tf/dtypes.md#int64"><code>tf.int64</code></a> scalar <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the
    number of times the dataset should be repeated. The default behavior
    (if `count` is `None` or `-1`) is for the dataset be repeated
    indefinitely.
* <b>`seed`</b>: (Optional.) A <a href="../../../tf/dtypes.md#int64"><code>tf.int64</code></a> scalar <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the
    random seed that will be used to create the distribution. See
    `tf.compat.v1.set_random_seed` for behavior.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.
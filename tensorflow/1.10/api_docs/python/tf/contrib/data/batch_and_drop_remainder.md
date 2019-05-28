<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.batch_and_drop_remainder" />
</div>

# tf.contrib.data.batch_and_drop_remainder

``` python
tf.contrib.data.batch_and_drop_remainder(batch_size)
```



Defined in [`tensorflow/contrib/data/python/ops/batching.py`](https://www.tensorflow.org/code/tensorflow/contrib/data/python/ops/batching.py).

See the guide: [Dataset Input Pipeline > Transformations on existing datasets](../../../../../api_guides/python/input_dataset.md#Transformations_on_existing_datasets)

A batching transformation that omits the final small batch (if present). (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.data.Dataset.batch(..., drop_remainder=True)`.

Like <a href="../../../tf/data/Dataset.md#batch"><code>tf.data.Dataset.batch</code></a>, this transformation combines
consecutive elements of this dataset into batches. However, if the batch
size does not evenly divide the input dataset size, this transformation will
drop the final smaller element.

The following example illustrates the difference between this
transformation and `Dataset.batch()`:

```python
dataset = tf.data.Dataset.range(200)
batched = dataset.apply(tf.contrib.data.batch_and_drop_remainder(128))
print(batched.output_shapes)  # ==> "(128,)" (the batch dimension is known)
```

By contrast, `dataset.batch(128)` would yield a two-element dataset with
shapes `(128,)` and `(72,)`, so the batch dimension would not be statically
known.

#### Args:

* <b>`batch_size`</b>: A <a href="../../../tf/int64.md"><code>tf.int64</code></a> scalar <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
      consecutive elements of this dataset to combine in a single batch.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>
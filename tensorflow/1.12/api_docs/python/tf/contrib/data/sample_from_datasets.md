<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.sample_from_datasets" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.data.sample_from_datasets

``` python
tf.contrib.data.sample_from_datasets(
    datasets,
    weights=None,
    seed=None
)
```



Defined in [`tensorflow/contrib/data/python/ops/interleave_ops.py`](/code/stable/tensorflow/contrib/data/python/ops/interleave_ops.py).

Samples elements at random from the datasets in `datasets`. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.data.experimental.sample_from_datasets(...)`.

#### Args:

* <b>`datasets`</b>: A list of <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> objects with compatible structure.
* <b>`weights`</b>: (Optional.) A list of `len(datasets)` floating-point values where
    `weights[i]` represents the probability with which an element should be
    sampled from `datasets[i]`, or a <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object where each
    element is such a list. Defaults to a uniform distribution across
    `datasets`.
* <b>`seed`</b>: (Optional.) A <a href="../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the
    random seed that will be used to create the distribution. See
    <a href="../../../tf/random/set_random_seed.md"><code>tf.set_random_seed</code></a> for behavior.


#### Returns:

A dataset that interleaves elements from `datasets` at random, according to
`weights` if provided, otherwise with uniform probability.


#### Raises:

* <b>`TypeError`</b>: If the `datasets` or `weights` arguments have the wrong type.
* <b>`ValueError`</b>: If the `weights` argument is specified and does not match the
    length of the `datasets` element.
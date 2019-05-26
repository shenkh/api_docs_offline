<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.rejection_resample" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.rejection_resample

``` python
tf.data.experimental.rejection_resample(
    class_func,
    target_dist,
    initial_dist=None,
    seed=None
)
```



Defined in [`tensorflow/python/data/experimental/ops/resampling.py`](/code/stable/tensorflow/python/data/experimental/ops/resampling.py).

A transformation that resamples a dataset to achieve a target distribution.

**NOTE** Resampling is performed via rejection sampling; some fraction
of the input values will be dropped.

#### Args:

* <b>`class_func`</b>: A function mapping an element of the input dataset to a scalar
    <a href="../../../tf.md#int32"><code>tf.int32</code></a> tensor. Values should be in `[0, num_classes)`.
* <b>`target_dist`</b>: A floating point type tensor, shaped `[num_classes]`.
* <b>`initial_dist`</b>: (Optional.)  A floating point type tensor, shaped
    `[num_classes]`.  If not provided, the true class distribution is
    estimated live in a streaming fashion.
* <b>`seed`</b>: (Optional.) Python integer seed for the resampler.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.nn.sufficient_statistics" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.nn.sufficient_statistics

Calculate the sufficient statistics for the mean and variance of `x`.

``` python
tf.compat.v1.nn.sufficient_statistics(
    x,
    axes,
    shift=None,
    keep_dims=None,
    name=None,
    keepdims=None
)
```



Defined in [`python/ops/nn_impl.py`](/code/stable/tensorflow/python/ops/nn_impl.py).

<!-- Placeholder for "Used in" -->

These sufficient statistics are computed using the one pass algorithm on
an input that's optionally shifted. See:
https://en.wikipedia.org/wiki/Algorithms_for_calculating_variance#Computing_shifted_data

#### Args:


* <b>`x`</b>: A `Tensor`.
* <b>`axes`</b>: Array of ints. Axes along which to compute mean and variance.
* <b>`shift`</b>: A `Tensor` containing the value by which to shift the data for
  numerical stability, or `None` if no shift is to be performed. A shift
  close to the true mean provides the most numerically stable results.
* <b>`keep_dims`</b>: produce statistics with the same dimensionality as the input.
* <b>`name`</b>: Name used to scope the operations that compute the sufficient stats.
* <b>`keepdims`</b>: Alias for keep_dims.


#### Returns:

Four `Tensor` objects of the same type as `x`:

* the count (number of elements to average over).
* the (possibly shifted) sum of the elements in the array.
* the (possibly shifted) sum of squares of the elements in the array.
* the shift by which the mean must be corrected or None if `shift` is None.

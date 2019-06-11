<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.random.stateless_normal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.random.stateless_normal

Outputs deterministic pseudorandom values from a normal distribution.

### Aliases:

* `tf.compat.v1.random.stateless_normal`
* `tf.compat.v2.random.stateless_normal`
* `tf.random.stateless_normal`

``` python
tf.random.stateless_normal(
    shape,
    seed,
    mean=0.0,
    stddev=1.0,
    dtype=tf.dtypes.float32,
    name=None
)
```



Defined in [`python/ops/stateless_random_ops.py`](/code/stable/tensorflow/python/ops/stateless_random_ops.py).

<!-- Placeholder for "Used in" -->

This is a stateless version of <a href="../../tf/random/normal.md"><code>tf.random.normal</code></a>: if run twice with the
same seeds, it will produce the same pseudorandom numbers.  The output is
consistent across multiple runs on the same hardware (and between CPU
and GPU), but may change between versions of TensorFlow or on non-CPU/GPU
hardware.

#### Args:


* <b>`shape`</b>: A 1-D integer Tensor or Python array. The shape of the output tensor.
* <b>`seed`</b>: A shape [2] integer Tensor of seeds to the random number generator.
* <b>`mean`</b>: A 0-D Tensor or Python value of type `dtype`. The mean of the normal
  distribution.
* <b>`stddev`</b>: A 0-D Tensor or Python value of type `dtype`. The standard deviation
  of the normal distribution.
* <b>`dtype`</b>: The type of the output.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A tensor of the specified shape filled with random normal values.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.random.truncated_normal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.random.truncated_normal

``` python
tf.random.truncated_normal(
    shape,
    mean=0.0,
    stddev=1.0,
    dtype=tf.dtypes.float32,
    seed=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/random_ops.py`](/code/stable/tensorflow/python/ops/random_ops.py).

Outputs random values from a truncated normal distribution.

The generated values follow a normal distribution with specified mean and
standard deviation, except that values whose magnitude is more than 2 standard
deviations from the mean are dropped and re-picked.

#### Args:

* <b>`shape`</b>: A 1-D integer Tensor or Python array. The shape of the output tensor.
* <b>`mean`</b>: A 0-D Tensor or Python value of type `dtype`. The mean of the
    truncated normal distribution.
* <b>`stddev`</b>: A 0-D Tensor or Python value of type `dtype`. The standard deviation
    of the normal distribution, before truncation.
* <b>`dtype`</b>: The type of the output.
* <b>`seed`</b>: A Python integer. Used to create a random seed for the distribution.
    See
    `tf.compat.v1.set_random_seed`
    for behavior.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A tensor of the specified shape filled with random truncated normal values.
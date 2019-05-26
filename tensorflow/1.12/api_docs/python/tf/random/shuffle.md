<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.random.shuffle" />
<meta itemprop="path" content="Stable" />
</div>

# tf.random.shuffle

### Aliases:

* `tf.random.shuffle`
* `tf.random_shuffle`

``` python
tf.random.shuffle(
    value,
    seed=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/random_ops.py`](/code/stable/tensorflow/python/ops/random_ops.py).

Randomly shuffles a tensor along its first dimension.

The tensor is shuffled along dimension 0, such that each `value[j]` is mapped
to one and only one `output[i]`. For example, a mapping that might occur for a
3x2 tensor is:

```python
[[1, 2],       [[5, 6],
 [3, 4],  ==>   [1, 2],
 [5, 6]]        [3, 4]]
```

#### Args:

* <b>`value`</b>: A Tensor to be shuffled.
* <b>`seed`</b>: A Python integer. Used to create a random seed for the distribution.
    See
    <a href="../../tf/random/set_random_seed.md"><code>tf.set_random_seed</code></a>
    for behavior.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A tensor of same shape and type as `value`, shuffled along its first
dimension.
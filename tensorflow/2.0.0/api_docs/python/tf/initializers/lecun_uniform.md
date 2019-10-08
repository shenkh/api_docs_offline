<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.initializers.lecun_uniform" />
<meta itemprop="path" content="Stable" />
</div>

# tf.initializers.lecun_uniform

### Aliases:

* `tf.initializers.lecun_uniform`
* `tf.keras.initializers.lecun_uniform`

``` python
tf.initializers.lecun_uniform(seed=None)
```



Defined in [`tensorflow/python/ops/init_ops_v2.py`](/code/stable/tensorflow/python/ops/init_ops_v2.py).

LeCun uniform initializer.

It draws samples from a uniform distribution within [-limit, limit]
where `limit` is `sqrt(3 / fan_in)`
where `fan_in` is the number of input units in the weight tensor.

#### Arguments:

* <b>`seed`</b>: A Python integer. Used to seed the random generator.


#### Returns:

  An initializer.

References:
    - Self-Normalizing Neural Networks,
    [Klambauer et al., 2017](https://papers.nips.cc/paper/6698-self-normalizing-neural-networks) # pylint: disable=line-too-long
    ([pdf](https://papers.nips.cc/paper/6698-self-normalizing-neural-networks.pdf))
    - Efficient Backprop,
    [Lecun et al., 1998](http://yann.lecun.com/exdb/publis/pdf/lecun-98b.pdf)
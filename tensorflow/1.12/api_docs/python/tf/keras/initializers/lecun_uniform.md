<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.initializers.lecun_uniform" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.initializers.lecun_uniform

### Aliases:

* `tf.initializers.lecun_uniform`
* `tf.keras.initializers.lecun_uniform`

``` python
tf.keras.initializers.lecun_uniform(seed=None)
```



Defined in [`tensorflow/python/ops/init_ops.py`](/code/stable/tensorflow/python/ops/init_ops.py).

LeCun uniform initializer.

It draws samples from a uniform distribution within [-limit, limit]
where `limit` is `sqrt(3 / fan_in)`
where `fan_in` is the number of input units in the weight tensor.

#### Arguments:

* <b>`seed`</b>: A Python integer. Used to seed the random generator.


#### Returns:

    An initializer.

References:
    LeCun 98, Efficient Backprop,
    http://yann.lecun.com/exdb/publis/pdf/lecun-98b.pdf
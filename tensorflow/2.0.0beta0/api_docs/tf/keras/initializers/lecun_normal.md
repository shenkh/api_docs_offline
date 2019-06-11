<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.initializers.lecun_normal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.initializers.lecun_normal

LeCun normal initializer.

### Aliases:

* `tf.compat.v2.initializers.lecun_normal`
* `tf.compat.v2.keras.initializers.lecun_normal`
* `tf.initializers.lecun_normal`
* `tf.keras.initializers.lecun_normal`

``` python
tf.keras.initializers.lecun_normal(seed=None)
```



Defined in [`python/ops/init_ops_v2.py`](/code/stable/tensorflow/python/ops/init_ops_v2.py).

<!-- Placeholder for "Used in" -->

It draws samples from a truncated normal distribution centered on 0
with `stddev = sqrt(1 / fan_in)`
where `fan_in` is the number of input units in the weight tensor.

#### Arguments:


* <b>`seed`</b>: A Python integer. Used to seed the random generator.


#### Returns:

An initializer.



#### References:

- Self-Normalizing Neural Networks,
[Klambauer et al., 2017]
(https://papers.nips.cc/paper/6698-self-normalizing-neural-networks)
([pdf]
(https://papers.nips.cc/paper/6698-self-normalizing-neural-networks.pdf))
- Efficient Backprop,
[Lecun et al., 1998](http://yann.lecun.com/exdb/publis/pdf/lecun-98b.pdf)

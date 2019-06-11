<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.keras.initializers.he_uniform" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.keras.initializers.he_uniform

He uniform variance scaling initializer.

### Aliases:

* `tf.compat.v1.initializers.he_uniform`
* `tf.compat.v1.keras.initializers.he_uniform`

``` python
tf.compat.v1.keras.initializers.he_uniform(seed=None)
```



Defined in [`python/ops/init_ops.py`](/code/stable/tensorflow/python/ops/init_ops.py).

<!-- Placeholder for "Used in" -->

It draws samples from a uniform distribution within [-limit, limit]
where `limit` is `sqrt(6 / fan_in)`
where `fan_in` is the number of input units in the weight tensor.

#### Arguments:


* <b>`seed`</b>: A Python integer. Used to seed the random generator.


#### Returns:

An initializer.



#### References:

[He et al., 2015]
(https://www.cv-foundation.org/openaccess/content_iccv_2015/html/He_Delving_Deep_into_ICCV_2015_paper.html)
# pylint: disable=line-too-long
([pdf](https://www.cv-foundation.org/openaccess/content_iccv_2015/papers/He_Delving_Deep_into_ICCV_2015_paper.pdf))

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.initializers.GlorotUniform" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.initializers.GlorotUniform

## Class `GlorotUniform`

Inherits From: [`VarianceScaling`](../../tf/initializers/VarianceScaling.md)

### Aliases:

* Class `tf.initializers.GlorotUniform`
* Class `tf.initializers.glorot_uniform`
* Class `tf.keras.initializers.GlorotUniform`
* Class `tf.keras.initializers.glorot_uniform`



Defined in [`tensorflow/python/ops/init_ops_v2.py`](/code/stable/tensorflow/python/ops/init_ops_v2.py).

The Glorot uniform initializer, also called Xavier uniform initializer.

It draws samples from a uniform distribution within [-limit, limit]
where `limit` is `sqrt(6 / (fan_in + fan_out))`
where `fan_in` is the number of input units in the weight tensor
and `fan_out` is the number of output units in the weight tensor.

#### Args:

* <b>`seed`</b>: A Python integer. Used to create random seeds. See
    `tf.compat.v1.set_random_seed`
    for behavior.

References:
    [Glorot et al., 2010](http://proceedings.mlr.press/v9/glorot10a.html)
    ([pdf](http://jmlr.org/proceedings/papers/v9/glorot10a/glorot10a.pdf))

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(seed=None)
```

Initialize self.  See help(type(self)) for accurate signature.



## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    shape,
    dtype=tf.dtypes.float32
)
```

Returns a tensor object initialized as specified by the initializer.

#### Args:

* <b>`shape`</b>: Shape of the tensor.
* <b>`dtype`</b>: Optional dtype of the tensor. Only floating point types are
   supported.


#### Raises:

* <b>`ValueError`</b>: If the dtype is not floating point

<h3 id="from_config"><code>from_config</code></h3>

``` python
from_config(
    cls,
    config
)
```

Instantiates an initializer from a configuration dictionary.

Example:

```python
initializer = RandomUniform(-1, 1)
config = initializer.get_config()
initializer = RandomUniform.from_config(config)
```

#### Args:

* <b>`config`</b>: A Python dictionary.
    It will typically be the output of `get_config`.


#### Returns:

An Initializer instance.

<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```

Returns the configuration of the initializer as a JSON-serializable dict.

#### Returns:

A JSON-serializable Python dict.




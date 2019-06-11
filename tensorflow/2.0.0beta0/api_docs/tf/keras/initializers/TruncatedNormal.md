<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.initializers.TruncatedNormal" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.keras.initializers.TruncatedNormal

## Class `TruncatedNormal`

Initializer that generates a truncated normal distribution.

Inherits From: [`Initializer`](../../../tf/keras/initializers/Initializer.md)

### Aliases:

* Class `tf.compat.v2.initializers.TruncatedNormal`
* Class `tf.compat.v2.keras.initializers.TruncatedNormal`
* Class `tf.initializers.TruncatedNormal`
* Class `tf.keras.initializers.TruncatedNormal`



Defined in [`python/ops/init_ops_v2.py`](/code/stable/tensorflow/python/ops/init_ops_v2.py).

<!-- Placeholder for "Used in" -->

These values are similar to values from a `random_normal_initializer`
except that values more than two standard deviations from the mean
are discarded and re-drawn. This is the recommended initializer for
neural network weights and filters.

#### Args:


* <b>`mean`</b>: a python scalar or a scalar tensor. Mean of the random values
  to generate.
* <b>`stddev`</b>: a python scalar or a scalar tensor. Standard deviation of the
  random values to generate.
* <b>`seed`</b>: A Python integer. Used to create random seeds. See
  <a href="../../../tf/compat/v1/set_random_seed.md"><code>tf.compat.v1.set_random_seed</code></a>
  for behavior.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    mean=0.0,
    stddev=0.05,
    seed=None
)
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


#### Example:



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





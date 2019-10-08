<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.random_uniform_initializer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.random_uniform_initializer

## Class `random_uniform_initializer`

Inherits From: [`Initializer`](../tf/initializers/Initializer.md)

### Aliases:

* Class `tf.initializers.RandomUniform`
* Class `tf.keras.initializers.RandomUniform`
* Class `tf.random_uniform_initializer`



Defined in [`tensorflow/python/ops/init_ops_v2.py`](/code/stable/tensorflow/python/ops/init_ops_v2.py).

Initializer that generates tensors with a uniform distribution.

#### Args:

* <b>`minval`</b>: A python scalar or a scalar tensor. Lower bound of the range
    of random values to generate.
* <b>`maxval`</b>: A python scalar or a scalar tensor. Upper bound of the range
    of random values to generate.  Defaults to 1 for float types.
* <b>`seed`</b>: A Python integer. Used to create random seeds. See
    `tf.compat.v1.set_random_seed`
    for behavior.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    minval=-0.05,
    maxval=0.05,
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
* <b>`dtype`</b>: Optional dtype of the tensor. Only floating point and integer
  types are supported.


#### Raises:

* <b>`ValueError`</b>: If the dtype is not numeric.

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




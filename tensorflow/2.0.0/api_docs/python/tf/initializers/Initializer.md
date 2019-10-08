<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.initializers.Initializer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.initializers.Initializer

## Class `Initializer`



### Aliases:

* Class `tf.initializers.Initializer`
* Class `tf.keras.initializers.Initializer`



Defined in [`tensorflow/python/ops/init_ops_v2.py`](/code/stable/tensorflow/python/ops/init_ops_v2.py).

Initializer base class: all initializers inherit from this class.
  

## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    shape,
    dtype=None
)
```

Returns a tensor object initialized as specified by the initializer.

#### Args:

* <b>`shape`</b>: Shape of the tensor.
* <b>`dtype`</b>: Optional dtype of the tensor. If not provided will return tensor
   of <a href="../../tf/dtypes.md#float32"><code>tf.float32</code></a>.

<h3 id="from_config"><code>from_config</code></h3>

``` python
@classmethod
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



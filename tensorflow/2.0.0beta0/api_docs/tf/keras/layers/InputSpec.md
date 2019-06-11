<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.InputSpec" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.keras.layers.InputSpec

## Class `InputSpec`

Specifies the ndim, dtype and shape of every input to a layer.



### Aliases:

* Class `tf.compat.v1.keras.layers.InputSpec`
* Class `tf.compat.v1.layers.InputSpec`
* Class `tf.compat.v2.keras.layers.InputSpec`
* Class `tf.keras.layers.InputSpec`



Defined in [`python/keras/engine/input_spec.py`](/code/stable/tensorflow/python/keras/engine/input_spec.py).

<!-- Placeholder for "Used in" -->

Every layer should expose (if appropriate) an `input_spec` attribute:
a list of instances of InputSpec (one per input tensor).

A None entry in a shape is compatible with any dimension,
a None shape is compatible with any shape.

#### Arguments:


* <b>`dtype`</b>: Expected DataType of the input.
* <b>`shape`</b>: Shape tuple, expected shape of the input
    (may include None for unchecked axes).
* <b>`ndim`</b>: Integer, expected rank of the input.
* <b>`max_ndim`</b>: Integer, maximum rank of the input.
* <b>`min_ndim`</b>: Integer, minimum rank of the input.
* <b>`axes`</b>: Dictionary mapping integer axes to
    a specific dimension value.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    dtype=None,
    shape=None,
    ndim=None,
    max_ndim=None,
    min_ndim=None,
    axes=None
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="from_config"><code>from_config</code></h3>

``` python
@classmethod
from_config(
    cls,
    config
)
```




<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```







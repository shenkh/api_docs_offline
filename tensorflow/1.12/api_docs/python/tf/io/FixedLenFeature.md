<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.FixedLenFeature" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="shape"/>
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="default_value"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.io.FixedLenFeature

## Class `FixedLenFeature`



### Aliases:

* Class `tf.FixedLenFeature`
* Class `tf.io.FixedLenFeature`



Defined in [`tensorflow/python/ops/parsing_ops.py`](/code/stable/tensorflow/python/ops/parsing_ops.py).

Configuration for parsing a fixed-length input feature.

To treat sparse input as dense, provide a `default_value`; otherwise,
the parse functions will fail on any examples missing this feature.

#### Fields:

* <b>`shape`</b>: Shape of input data.
* <b>`dtype`</b>: Data type of input.
* <b>`default_value`</b>: Value to be used if an example is missing this feature. It
      must be compatible with `dtype` and of the specified `shape`.

<h2 id="__new__"><code>__new__</code></h2>

``` python
@staticmethod
__new__(
    cls,
    shape,
    dtype,
    default_value=None
)
```

Create new instance of FixedLenFeature(shape, dtype, default_value)



## Properties

<h3 id="shape"><code>shape</code></h3>



<h3 id="dtype"><code>dtype</code></h3>



<h3 id="default_value"><code>default_value</code></h3>






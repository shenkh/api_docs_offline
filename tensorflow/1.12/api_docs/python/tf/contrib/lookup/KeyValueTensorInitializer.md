<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.lookup.KeyValueTensorInitializer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="key_dtype"/>
<meta itemprop="property" content="value_dtype"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="initialize"/>
</div>

# tf.contrib.lookup.KeyValueTensorInitializer

## Class `KeyValueTensorInitializer`

Inherits From: [`TableInitializerBase`](../../../tf/contrib/lookup/TableInitializerBase.md)



Defined in [`tensorflow/python/ops/lookup_ops.py`](/code/stable/tensorflow/python/ops/lookup_ops.py).

Table initializers given `keys` and `values` tensors.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    keys,
    values,
    key_dtype=None,
    value_dtype=None,
    name=None
)
```

Constructs a table initializer object based on keys and values tensors.

#### Args:

* <b>`keys`</b>: The tensor for the keys.
* <b>`values`</b>: The tensor for the values.
* <b>`key_dtype`</b>: The `keys` data type. Used when `keys` is a python array.
* <b>`value_dtype`</b>: The `values` data type. Used when `values` is a python array.
* <b>`name`</b>: A name for the operation (optional).



## Properties

<h3 id="key_dtype"><code>key_dtype</code></h3>

The expected table key dtype.

<h3 id="value_dtype"><code>value_dtype</code></h3>

The expected table value dtype.



## Methods

<h3 id="initialize"><code>initialize</code></h3>

``` python
initialize(table)
```

Initializes the given `table` with `keys` and `values` tensors.

#### Args:

* <b>`table`</b>: The table to initialize.


#### Returns:

The operation that initializes the table.


#### Raises:

* <b>`TypeError`</b>: when the keys and values data types do not match the table
  key and value data types.




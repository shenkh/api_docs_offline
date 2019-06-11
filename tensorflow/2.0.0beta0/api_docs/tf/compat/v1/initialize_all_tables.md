<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.initialize_all_tables" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.initialize_all_tables

Returns an Op that initializes all tables of the default graph. (deprecated)

``` python
tf.compat.v1.initialize_all_tables(name='init_all_tables')
```



Defined in [`python/ops/lookup_ops.py`](/code/stable/tensorflow/python/ops/lookup_ops.py).

<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.tables_initializer` instead.

#### Args:


* <b>`name`</b>: Optional name for the initialization op.


#### Returns:

An Op that initializes all tables.  Note that if there are
not tables the returned Op is a NoOp.

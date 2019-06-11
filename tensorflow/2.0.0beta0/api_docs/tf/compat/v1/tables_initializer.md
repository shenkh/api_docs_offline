<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.tables_initializer" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.tables_initializer

Returns an Op that initializes all tables of the default graph.

### Aliases:

* `tf.compat.v1.initializers.tables_initializer`
* `tf.compat.v1.tables_initializer`

``` python
tf.compat.v1.tables_initializer(name='init_all_tables')
```



Defined in [`python/ops/lookup_ops.py`](/code/stable/tensorflow/python/ops/lookup_ops.py).

<!-- Placeholder for "Used in" -->

See the [Low Level
Intro](https://www.tensorflow.org/guide/low_level_intro#feature_columns)
guide, for an example of usage.

#### Args:


* <b>`name`</b>: Optional name for the initialization op.


#### Returns:

An Op that initializes all tables.  Note that if there are
not tables the returned Op is a NoOp.

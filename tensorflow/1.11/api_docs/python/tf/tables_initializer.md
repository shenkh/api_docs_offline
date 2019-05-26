<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.tables_initializer" />
<meta itemprop="path" content="Stable" />
</div>

# tf.tables_initializer

``` python
tf.tables_initializer(name='init_all_tables')
```



Defined in [`tensorflow/python/ops/lookup_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/lookup_ops.py).

Returns an Op that initializes all tables of the default graph.

#### Args:

* <b>`name`</b>: Optional name for the initialization op.


#### Returns:

An Op that initializes all tables.  Note that if there are
not tables the returned Op is a NoOp.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.saved_model.main_op.main_op" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.saved_model.main_op.main_op

Returns a main op to init variables and tables. (deprecated)

``` python
tf.compat.v1.saved_model.main_op.main_op()
```



Defined in [`python/saved_model/main_op_impl.py`](/code/stable/tensorflow/python/saved_model/main_op_impl.py).

<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
This function will only be available through the v1 compatibility library as tf.compat.v1.saved_model.main_op.main_op.

Returns the main op including the group of ops that initializes all
variables, initializes local variables and initialize all tables.

#### Returns:

The set of ops to be run as part of the main op upon the load operation.

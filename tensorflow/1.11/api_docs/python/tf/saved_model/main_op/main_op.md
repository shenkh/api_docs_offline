<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.saved_model.main_op.main_op" />
<meta itemprop="path" content="Stable" />
</div>

# tf.saved_model.main_op.main_op

``` python
tf.saved_model.main_op.main_op()
```



Defined in [`tensorflow/python/saved_model/main_op_impl.py`](https://www.tensorflow.org/code/tensorflow/python/saved_model/main_op_impl.py).

Returns a main op to init variables and tables.

Returns the main op including the group of ops that initializes all
variables, initializes local variables and initialize all tables.

#### Returns:

The set of ops to be run as part of the main op upon the load operation.
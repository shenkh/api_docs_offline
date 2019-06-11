<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.keras.backend.get_session" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.keras.backend.get_session

Returns the TF session to be used by the backend.

``` python
tf.compat.v1.keras.backend.get_session(op_input_list=())
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->

If a default TensorFlow session is available, we will return it.

Else, we will return the global Keras session assuming it matches
the current graph.

If no global Keras session exists at this point:
we will create a new global session.

Note that you can manually set the global session
via `K.set_session(sess)`.

#### Arguments:


* <b>`op_input_list`</b>: An option sequence of tensors or ops, which will be used
  to determine the current graph. Otherwise the default graph will be
  used.


#### Returns:

A TensorFlow session.

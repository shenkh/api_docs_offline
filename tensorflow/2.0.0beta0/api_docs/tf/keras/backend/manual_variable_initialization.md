<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.manual_variable_initialization" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.manual_variable_initialization

Sets the manual variable initialization flag.

### Aliases:

* `tf.compat.v1.keras.backend.manual_variable_initialization`
* `tf.compat.v2.keras.backend.manual_variable_initialization`
* `tf.keras.backend.manual_variable_initialization`

``` python
tf.keras.backend.manual_variable_initialization(value)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->

This boolean flag determines whether
variables should be initialized
as they are instantiated (default), or if
the user should handle the initialization
(e.g. via `tf.compat.v1.initialize_all_variables()`).

#### Arguments:


* <b>`value`</b>: Python boolean.
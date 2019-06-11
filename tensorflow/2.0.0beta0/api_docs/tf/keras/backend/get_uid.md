<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.get_uid" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.get_uid

Associates a string prefix with an integer counter in a TensorFlow graph.

### Aliases:

* `tf.compat.v1.keras.backend.get_uid`
* `tf.compat.v2.keras.backend.get_uid`
* `tf.keras.backend.get_uid`

``` python
tf.keras.backend.get_uid(prefix='')
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`prefix`</b>: String prefix to index.


#### Returns:

Unique integer ID.



#### Example:



```
  >>> get_uid('dense')
  1
  >>> get_uid('dense')
  2
```
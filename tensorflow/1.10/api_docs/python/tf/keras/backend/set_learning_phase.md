<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.set_learning_phase" />
</div>

# tf.keras.backend.set_learning_phase

``` python
tf.keras.backend.set_learning_phase(value)
```



Defined in [`tensorflow/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/backend.py).

Sets the learning phase to a fixed value.

#### Arguments:

* <b>`value`</b>: Learning phase value, either 0 or 1 (integers).


#### Raises:

* <b>`ValueError`</b>: if `value` is neither `0` nor `1`.
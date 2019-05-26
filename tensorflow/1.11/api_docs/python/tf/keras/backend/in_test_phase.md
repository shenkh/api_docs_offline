<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.in_test_phase" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.in_test_phase

``` python
tf.keras.backend.in_test_phase(
    x,
    alt,
    training=None
)
```



Defined in [`tensorflow/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/backend.py).

Selects `x` in test phase, and `alt` otherwise.

Note that `alt` should have the *same shape* as `x`.

#### Arguments:

* <b>`x`</b>: What to return in test phase
        (tensor or callable that returns a tensor).
* <b>`alt`</b>: What to return otherwise
        (tensor or callable that returns a tensor).
* <b>`training`</b>: Optional scalar tensor
        (or Python boolean, or Python integer)
        specifying the learning phase.


#### Returns:

Either `x` or `alt` based on `K.learning_phase`.
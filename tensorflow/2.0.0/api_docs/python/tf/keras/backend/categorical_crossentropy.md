<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.categorical_crossentropy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.categorical_crossentropy

``` python
tf.keras.backend.categorical_crossentropy(
    target,
    output,
    from_logits=False,
    axis=-1
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Categorical crossentropy between an output tensor and a target tensor.

#### Arguments:

* <b>`target`</b>: A tensor of the same shape as `output`.
* <b>`output`</b>: A tensor resulting from a softmax
        (unless `from_logits` is True, in which
        case `output` is expected to be the logits).
* <b>`from_logits`</b>: Boolean, whether `output` is the
        result of a softmax, or is a tensor of logits.
* <b>`axis`</b>: Int specifying the channels axis. `axis=-1` corresponds to data
        format `channels_last', and `axis=1` corresponds to data format
        `channels_first`.


#### Returns:

Output tensor.


#### Raises:

* <b>`ValueError`</b>: if `axis` is neither -1 nor one of the axes of `output`.

Example:
```python:
    import tensorflow as tf
    from tensorflow.keras import backend as K
    a = tf.constant([1., 0., 0., 0., 1., 0., 0., 0., 1.], shape=[3,3])
    print("a: ", a)
    b = tf.constant([.9, .05, .05, .5, .89, .6, .05, .01, .94], shape=[3,3])
    print("b: ", b)
    loss = K.categorical_crossentropy(a, b)
    print('Loss: ', loss) #Loss: tf.Tensor([0.10536055 0.8046684  0.06187541], shape=(3,), dtype=float32)
    loss = K.categorical_crossentropy(a, a)
    print('Loss: ', loss) #Loss:  tf.Tensor([1.1920929e-07 1.1920929e-07 1.1920929e-07], shape=(3,), dtype=float32)
```
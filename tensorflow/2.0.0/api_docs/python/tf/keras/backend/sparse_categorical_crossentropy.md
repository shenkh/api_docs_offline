<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.sparse_categorical_crossentropy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.sparse_categorical_crossentropy

``` python
tf.keras.backend.sparse_categorical_crossentropy(
    target,
    output,
    from_logits=False,
    axis=-1
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Categorical crossentropy with integer targets.

#### Arguments:

* <b>`target`</b>: An integer tensor.
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
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.binary_crossentropy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.binary_crossentropy

Binary crossentropy between an output tensor and a target tensor.

### Aliases:

* `tf.compat.v1.keras.backend.binary_crossentropy`
* `tf.compat.v2.keras.backend.binary_crossentropy`
* `tf.keras.backend.binary_crossentropy`

``` python
tf.keras.backend.binary_crossentropy(
    target,
    output,
    from_logits=False
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`target`</b>: A tensor with the same shape as `output`.
* <b>`output`</b>: A tensor.
* <b>`from_logits`</b>: Whether `output` is expected to be a logits tensor.
    By default, we consider that `output`
    encodes a probability distribution.


#### Returns:

A tensor.

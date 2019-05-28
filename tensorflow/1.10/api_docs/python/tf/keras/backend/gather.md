<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.gather" />
</div>

# tf.keras.backend.gather

``` python
tf.keras.backend.gather(
    reference,
    indices
)
```



Defined in [`tensorflow/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/backend.py).

Retrieves the elements of indices `indices` in the tensor `reference`.

#### Arguments:

* <b>`reference`</b>: A tensor.
* <b>`indices`</b>: An integer tensor of indices.


#### Returns:

A tensor of same type as `reference`.
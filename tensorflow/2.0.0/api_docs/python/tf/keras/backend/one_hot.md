<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.one_hot" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.one_hot

``` python
tf.keras.backend.one_hot(
    indices,
    num_classes
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Computes the one-hot representation of an integer tensor.

#### Arguments:

* <b>`indices`</b>: nD integer tensor of shape
        `(batch_size, dim1, dim2, ... dim(n-1))`
* <b>`num_classes`</b>: Integer, number of classes to consider.


#### Returns:

(n + 1)D one hot representation of the input
with shape `(batch_size, dim1, dim2, ... dim(n-1), num_classes)`


#### Returns:

The one-hot tensor.
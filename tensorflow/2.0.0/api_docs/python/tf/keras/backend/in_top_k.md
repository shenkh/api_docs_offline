<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.in_top_k" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.in_top_k

``` python
tf.keras.backend.in_top_k(
    predictions,
    targets,
    k
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Returns whether the `targets` are in the top `k` `predictions`.

#### Arguments:

* <b>`predictions`</b>: A tensor of shape `(batch_size, classes)` and type `float32`.
* <b>`targets`</b>: A 1D tensor of length `batch_size` and type `int32` or `int64`.
* <b>`k`</b>: An `int`, number of top elements to consider.


#### Returns:

A 1D tensor of length `batch_size` and type `bool`.
`output[i]` is `True` if `predictions[i, targets[i]]` is within top-`k`
values of `predictions[i]`.
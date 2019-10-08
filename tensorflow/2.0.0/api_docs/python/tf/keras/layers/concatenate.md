<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.concatenate" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.layers.concatenate

``` python
tf.keras.layers.concatenate(
    inputs,
    axis=-1,
    **kwargs
)
```



Defined in [`tensorflow/python/keras/layers/merge.py`](/code/stable/tensorflow/python/keras/layers/merge.py).

Functional interface to the `Concatenate` layer.

#### Arguments:

* <b>`inputs`</b>: A list of input tensors (at least 2).
* <b>`axis`</b>: Concatenation axis.
* <b>`**kwargs`</b>: Standard layer keyword arguments.


#### Returns:

A tensor, the concatenation of the inputs alongside axis `axis`.
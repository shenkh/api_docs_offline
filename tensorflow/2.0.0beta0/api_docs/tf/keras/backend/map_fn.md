<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.map_fn" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.map_fn

Map the function fn over the elements elems and return the outputs.

### Aliases:

* `tf.compat.v1.keras.backend.map_fn`
* `tf.compat.v2.keras.backend.map_fn`
* `tf.keras.backend.map_fn`

``` python
tf.keras.backend.map_fn(
    fn,
    elems,
    name=None,
    dtype=None
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`fn`</b>: Callable that will be called upon each element in elems
* <b>`elems`</b>: tensor
* <b>`name`</b>: A string name for the map node in the graph
* <b>`dtype`</b>: Output data type.


#### Returns:

Tensor with dtype `dtype`.

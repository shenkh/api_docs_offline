<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.foldr" />
</div>

# tf.keras.backend.foldr

``` python
tf.keras.backend.foldr(
    fn,
    elems,
    initializer=None,
    name=None
)
```



Defined in [`tensorflow/python/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/backend.py).

Reduce elems using fn to combine them from right to left.

#### Arguments:

* <b>`fn`</b>: Callable that will be called upon each element in elems and an
        accumulator, for instance `lambda acc, x: acc + x`
* <b>`elems`</b>: tensor
* <b>`initializer`</b>: The first value used (`elems[-1]` in case of None)
* <b>`name`</b>: A string name for the foldr node in the graph


#### Returns:

Same type and shape as initializer
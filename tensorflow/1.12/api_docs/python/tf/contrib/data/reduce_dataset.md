<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.reduce_dataset" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.data.reduce_dataset

``` python
tf.contrib.data.reduce_dataset(
    dataset,
    reducer
)
```



Defined in [`tensorflow/contrib/data/python/ops/get_single_element.py`](/code/stable/tensorflow/contrib/data/python/ops/get_single_element.py).

Returns the result of reducing the `dataset` using `reducer`. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.data.Dataset.reduce(...)`.

#### Args:

* <b>`dataset`</b>: A <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object.
* <b>`reducer`</b>: A <a href="../../../tf/contrib/data/Reducer.md"><code>tf.contrib.data.Reducer</code></a> object representing the reduce logic.


#### Returns:

A nested structure of <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> objects, corresponding to the result
of reducing `dataset` using `reducer`.


#### Raises:

* <b>`TypeError`</b>: if `dataset` is not a <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object.
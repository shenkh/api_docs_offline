<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.get_single_element" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.get_single_element

``` python
tf.data.experimental.get_single_element(dataset)
```



Defined in [`tensorflow/python/data/experimental/ops/get_single_element.py`](/code/stable/tensorflow/python/data/experimental/ops/get_single_element.py).

Returns the single element in `dataset` as a nested structure of tensors.

This function enables you to use a <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> in a stateless
"tensor-in tensor-out" expression, without creating a
`tf.compat.v1.data.Iterator`.
This can be useful when your preprocessing transformations are expressed
as a `Dataset`, and you want to use the transformation at serving time.
For example:

```python
input_batch = tf.compat.v1.placeholder(tf.string, shape=[BATCH_SIZE])

def preprocessing_fn(input_str):
  # ...
  return image, label

dataset = (tf.data.Dataset.from_tensor_slices(input_batch)
           .map(preprocessing_fn, num_parallel_calls=BATCH_SIZE)
           .batch(BATCH_SIZE))

image_batch, label_batch = tf.data.experimental.get_single_element(dataset)
```

#### Args:

* <b>`dataset`</b>: A <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object containing a single element.


#### Returns:

A nested structure of <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> objects, corresponding to the single
element of `dataset`.


#### Raises:

* <b>`TypeError`</b>: if `dataset` is not a <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object.
  InvalidArgumentError (at runtime): if `dataset` does not contain exactly
    one element.
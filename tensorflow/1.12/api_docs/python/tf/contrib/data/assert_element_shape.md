<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.assert_element_shape" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.data.assert_element_shape

``` python
tf.contrib.data.assert_element_shape(expected_shapes)
```



Defined in [`tensorflow/contrib/data/python/ops/batching.py`](/code/stable/tensorflow/contrib/data/python/ops/batching.py).

Assert the shape of this `Dataset`.

```python
shapes = [tf.TensorShape([16, 256]), tf.TensorShape([None, 2])]
result = dataset.apply(tf.contrib.data.assert_element_shape(shapes))
print(result.output_shapes)  # ==> "((16, 256), (<unknown>, 2))"
```

If dataset shapes and expected_shape, are fully defined, assert they match.
Otherwise, add assert op that will validate the shapes when tensors are
evaluated, and set shapes on tensors, respectively.

Note that unknown dimension in `expected_shapes` will be ignored.

#### Args:

* <b>`expected_shapes`</b>: A nested structure of <a href="../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> objects.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>
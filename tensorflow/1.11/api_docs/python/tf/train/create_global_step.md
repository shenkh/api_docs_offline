<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.create_global_step" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.create_global_step

``` python
tf.train.create_global_step(graph=None)
```



Defined in [`tensorflow/python/training/training_util.py`](https://www.tensorflow.org/code/tensorflow/python/training/training_util.py).

Create global step tensor in graph.

#### Args:

* <b>`graph`</b>: The graph in which to create the global step tensor. If missing,
    use default graph.


#### Returns:

Global step tensor.


#### Raises:

* <b>`ValueError`</b>: if global step tensor is already defined.
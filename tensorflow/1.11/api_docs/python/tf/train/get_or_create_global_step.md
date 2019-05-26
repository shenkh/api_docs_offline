<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.get_or_create_global_step" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.get_or_create_global_step

``` python
tf.train.get_or_create_global_step(graph=None)
```



Defined in [`tensorflow/python/training/training_util.py`](https://www.tensorflow.org/code/tensorflow/python/training/training_util.py).

Returns and create (if necessary) the global step tensor.

#### Args:

* <b>`graph`</b>: The graph in which to create the global step tensor. If missing, use
    default graph.


#### Returns:

The global step tensor.
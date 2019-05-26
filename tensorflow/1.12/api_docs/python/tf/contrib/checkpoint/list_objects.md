<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.checkpoint.list_objects" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.checkpoint.list_objects

``` python
tf.contrib.checkpoint.list_objects(root_checkpointable)
```



Defined in [`tensorflow/python/training/checkpointable/util.py`](/code/stable/tensorflow/python/training/checkpointable/util.py).

Traverse the object graph and list all accessible objects.

Looks for `Checkpointable` objects which are dependencies of
`root_checkpointable`. Includes slot variables only if the variable they are
slotting for and the optimizer are dependencies of `root_checkpointable`
(i.e. if they would be saved with a checkpoint).

#### Args:

* <b>`root_checkpointable`</b>: A `Checkpointable` object whose dependencies should be
    flattened.

#### Returns:

A flat list of objects.
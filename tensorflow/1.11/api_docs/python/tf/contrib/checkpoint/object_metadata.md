<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.checkpoint.object_metadata" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.checkpoint.object_metadata

``` python
tf.contrib.checkpoint.object_metadata(save_path)
```



Defined in [`tensorflow/python/training/checkpointable/util.py`](https://www.tensorflow.org/code/tensorflow/python/training/checkpointable/util.py).

Retrieves information about the objects in a checkpoint.

Example usage:

```python
object_graph = tf.contrib.checkpoint.object_metadata(
    tf.train.latest_checkpoint(checkpoint_directory))
ckpt_variable_names = set()
for node in object_graph.nodes:
  for attribute in node.attributes:
    ckpt_variable_names.add(attribute.full_name)
```

#### Args:

* <b>`save_path`</b>: The path to the checkpoint, as returned by `save` or
    <a href="../../../tf/train/latest_checkpoint.md"><code>tf.train.latest_checkpoint</code></a>.

#### Returns:

A parsed <a href="../../../tf/contrib/checkpoint/CheckpointableObjectGraph.md"><code>tf.contrib.checkpoint.CheckpointableObjectGraph</code></a> protocol buffer.

#### Raises:

* <b>`ValueError`</b>: If an object graph was not found in the checkpoint.
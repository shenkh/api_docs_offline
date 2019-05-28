<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.write_graph" />
</div>

# tf.train.write_graph

``` python
tf.train.write_graph(
    graph_or_graph_def,
    logdir,
    name,
    as_text=True
)
```



Defined in [`tensorflow/python/framework/graph_io.py`](https://www.tensorflow.org/code/tensorflow/python/framework/graph_io.py).

See the guide: [Training > Training Utilities](../../../../api_guides/python/train.md#Training_Utilities)

Writes a graph proto to a file.

The graph is written as a text proto unless `as_text` is `False`.

```python
v = tf.Variable(0, name='my_variable')
sess = tf.Session()
tf.train.write_graph(sess.graph_def, '/tmp/my-model', 'train.pbtxt')
```

or

```python
v = tf.Variable(0, name='my_variable')
sess = tf.Session()
tf.train.write_graph(sess.graph, '/tmp/my-model', 'train.pbtxt')
```

#### Args:

* <b>`graph_or_graph_def`</b>: A `Graph` or a `GraphDef` protocol buffer.
* <b>`logdir`</b>: Directory where to write the graph. This can refer to remote
    filesystems, such as Google Cloud Storage (GCS).
* <b>`name`</b>: Filename for the graph.
* <b>`as_text`</b>: If `True`, writes the graph as an ASCII proto.


#### Returns:

The path of the output proto file.
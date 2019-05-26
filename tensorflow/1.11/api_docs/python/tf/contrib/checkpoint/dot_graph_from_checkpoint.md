<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.checkpoint.dot_graph_from_checkpoint" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.checkpoint.dot_graph_from_checkpoint

``` python
tf.contrib.checkpoint.dot_graph_from_checkpoint(save_path)
```



Defined in [`tensorflow/contrib/checkpoint/python/visualize.py`](https://www.tensorflow.org/code/tensorflow/contrib/checkpoint/python/visualize.py).

Visualizes an object-based checkpoint (from <a href="../../../tf/train/Checkpoint.md"><code>tf.train.Checkpoint</code></a>).

Useful for inspecting checkpoints and debugging loading issues.

Example usage from Python (requires pydot):
```python
import tensorflow as tf
import pydot

dot_string = tf.contrib.checkpoint.dot_graph_from_checkpoint('/path/to/ckpt')
parsed, = pydot.graph_from_dot_data(dot_string)
parsed.write_svg('/tmp/tensorflow/visualized_checkpoint.svg')
```

Example command line usage:
```sh
python -c "import tensorflow as tf;\
  print(tf.contrib.checkpoint.dot_graph_from_checkpoint('/path/to/ckpt'))"\
  | dot -Tsvg > /tmp/tensorflow/checkpoint_viz.svg
```

#### Args:

* <b>`save_path`</b>: The checkpoint prefix, as returned by <a href="../../../tf/train/Checkpoint.md#save"><code>tf.train.Checkpoint.save</code></a>
    or <a href="../../../tf/train/latest_checkpoint.md"><code>tf.train.latest_checkpoint</code></a>.

#### Returns:

A graph in DOT format as a string.
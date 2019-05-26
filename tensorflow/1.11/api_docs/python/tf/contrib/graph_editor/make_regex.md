<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.make_regex" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.graph_editor.make_regex

``` python
tf.contrib.graph_editor.make_regex(obj)
```



Defined in [`tensorflow/contrib/graph_editor/select.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/select.py).

Return a compiled regular expression.

#### Args:

* <b>`obj`</b>: a string or a regular expression.

#### Returns:

A compiled regular expression.

#### Raises:

* <b>`ValueError`</b>: if obj could not be converted to a regular expression.
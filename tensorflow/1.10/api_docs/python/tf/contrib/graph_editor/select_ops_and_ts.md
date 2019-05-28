<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.graph_editor.select_ops_and_ts" />
</div>

# tf.contrib.graph_editor.select_ops_and_ts

``` python
tf.contrib.graph_editor.select_ops_and_ts(
    *args,
    **kwargs
)
```



Defined in [`tensorflow/contrib/graph_editor/select.py`](https://www.tensorflow.org/code/tensorflow/contrib/graph_editor/select.py).

See the guide: [Graph Editor (contrib) > Module: select](../../../../../api_guides/python/contrib.graph_editor.md#Module_select)

Helper to select operations and tensors.

#### Args:

* <b>`*args`</b>: list of 1) regular expressions (compiled or not) or 2) (array of)
    <a href="../../../tf/Operation.md"><code>tf.Operation</code></a> 3) (array of) tf.Tensor. Regular expressions matching
    tensors must start with the comment `"(?#ts)"`, for instance:
    `"(?#ts)^foo/.*"`.
* <b>`**kwargs`</b>: 'graph': <a href="../../../tf/Graph.md"><code>tf.Graph</code></a> in which to perform the regex query.This is
    required when using regex.
    'positive_filter': an elem if selected only if `positive_filter(elem)` is
      `True`. This is optional.

#### Returns:

A tuple `(ops, ts)` where:
  `ops` is a list of <a href="../../../tf/Operation.md"><code>tf.Operation</code></a>, and
  `ts` is a list of <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>

#### Raises:

* <b>`TypeError`</b>: if the optional keyword argument graph is not a <a href="../../../tf/Graph.md"><code>tf.Graph</code></a>
    or if an argument in args is not an (array of) <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>
    or an (array of) <a href="../../../tf/Operation.md"><code>tf.Operation</code></a> or a string or a regular expression.
* <b>`ValueError`</b>: if one of the keyword arguments is unexpected or if a regular
    expression is used without passing a graph as a keyword argument.
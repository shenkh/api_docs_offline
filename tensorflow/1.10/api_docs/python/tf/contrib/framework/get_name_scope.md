<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.get_name_scope" />
</div>

# tf.contrib.framework.get_name_scope

``` python
tf.contrib.framework.get_name_scope()
```



Defined in [`tensorflow/contrib/framework/python/ops/ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/ops/ops.py).

Returns the current name scope of the default graph.

For example:

  ```python
  with tf.name_scope('scope1'):
    with tf.name_scope('scope2'):
      print(tf.contrib.framework.get_name_scope())
  ```
  would print the string `scope1/scope2`.

#### Returns:

A string representing the current name scope.
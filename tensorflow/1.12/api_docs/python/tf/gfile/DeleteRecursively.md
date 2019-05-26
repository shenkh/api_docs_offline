<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.gfile.DeleteRecursively" />
<meta itemprop="path" content="Stable" />
</div>

# tf.gfile.DeleteRecursively

``` python
tf.gfile.DeleteRecursively(dirname)
```



Defined in [`tensorflow/python/lib/io/file_io.py`](/code/stable/tensorflow/python/lib/io/file_io.py).

Deletes everything under dirname recursively.

#### Args:

* <b>`dirname`</b>: string, a path to a directory


#### Raises:

* <b>`errors.OpError`</b>: If the operation fails.
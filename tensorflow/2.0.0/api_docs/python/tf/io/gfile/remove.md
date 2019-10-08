<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.gfile.remove" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.gfile.remove

``` python
tf.io.gfile.remove(path)
```



Defined in [`tensorflow/python/lib/io/file_io.py`](/code/stable/tensorflow/python/lib/io/file_io.py).

Deletes the path located at 'path'.

#### Args:

* <b>`path`</b>: string, a path


#### Raises:

* <b>`errors.OpError`</b>: Propagates any errors reported by the FileSystem API.  E.g.,
  NotFoundError if the path does not exist.
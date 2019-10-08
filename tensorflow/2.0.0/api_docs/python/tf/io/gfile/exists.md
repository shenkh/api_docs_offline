<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.gfile.exists" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.gfile.exists

``` python
tf.io.gfile.exists(path)
```



Defined in [`tensorflow/python/lib/io/file_io.py`](/code/stable/tensorflow/python/lib/io/file_io.py).

Determines whether a path exists or not.

#### Args:

* <b>`path`</b>: string, a path


#### Returns:

True if the path exists, whether it's a file or a directory.
False if the path does not exist and there are no filesystem errors.


#### Raises:

* <b>`errors.OpError`</b>: Propagates any errors reported by the FileSystem API.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.gfile.Exists" />
<meta itemprop="path" content="Stable" />
</div>

# tf.gfile.Exists

``` python
tf.gfile.Exists(filename)
```



Defined in [`tensorflow/python/lib/io/file_io.py`](/code/stable/tensorflow/python/lib/io/file_io.py).

Determines whether a path exists or not.

#### Args:

* <b>`filename`</b>: string, a path


#### Returns:

True if the path exists, whether its a file or a directory.
False if the path does not exist and there are no filesystem errors.


#### Raises:

* <b>`errors.OpError`</b>: Propagates any errors reported by the FileSystem API.
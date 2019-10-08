<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.gfile.makedirs" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.gfile.makedirs

``` python
tf.io.gfile.makedirs(path)
```



Defined in [`tensorflow/python/lib/io/file_io.py`](/code/stable/tensorflow/python/lib/io/file_io.py).

Creates a directory and all parent/intermediate directories.

It succeeds if path already exists and is writable.

#### Args:

* <b>`path`</b>: string, name of the directory to be created


#### Raises:

* <b>`errors.OpError`</b>: If the operation fails.
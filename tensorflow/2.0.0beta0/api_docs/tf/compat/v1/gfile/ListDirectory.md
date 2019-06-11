<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.gfile.ListDirectory" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.gfile.ListDirectory

Returns a list of entries contained within a directory.

``` python
tf.compat.v1.gfile.ListDirectory(dirname)
```



Defined in [`python/lib/io/file_io.py`](/code/stable/tensorflow/python/lib/io/file_io.py).

<!-- Placeholder for "Used in" -->

The list is in arbitrary order. It does not contain the special entries "."
and "..".

#### Args:


* <b>`dirname`</b>: string, path to a directory


#### Returns:

[filename1, filename2, ... filenameN] as strings



#### Raises:

errors.NotFoundError if directory doesn't exist

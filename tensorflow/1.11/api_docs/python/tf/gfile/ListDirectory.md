<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.gfile.ListDirectory" />
<meta itemprop="path" content="Stable" />
</div>

# tf.gfile.ListDirectory

``` python
tf.gfile.ListDirectory(dirname)
```



Defined in [`tensorflow/python/lib/io/file_io.py`](https://www.tensorflow.org/code/tensorflow/python/lib/io/file_io.py).

Returns a list of entries contained within a directory.

The list is in arbitrary order. It does not contain the special entries "."
and "..".

#### Args:

* <b>`dirname`</b>: string, path to a directory


#### Returns:

[filename1, filename2, ... filenameN] as strings


#### Raises:

errors.NotFoundError if directory doesn't exist
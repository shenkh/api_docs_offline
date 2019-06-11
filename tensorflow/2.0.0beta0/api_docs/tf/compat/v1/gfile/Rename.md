<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.gfile.Rename" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.gfile.Rename

Rename or move a file / directory.

``` python
tf.compat.v1.gfile.Rename(
    oldname,
    newname,
    overwrite=False
)
```



Defined in [`python/lib/io/file_io.py`](/code/stable/tensorflow/python/lib/io/file_io.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`oldname`</b>: string, pathname for a file
* <b>`newname`</b>: string, pathname to which the file needs to be moved
* <b>`overwrite`</b>: boolean, if false it's an error for `newname` to be occupied by
  an existing file.


#### Raises:


* <b>`errors.OpError`</b>: If the operation fails.
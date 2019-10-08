<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.gfile.rename" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.gfile.rename

``` python
tf.io.gfile.rename(
    src,
    dst,
    overwrite=False
)
```



Defined in [`tensorflow/python/lib/io/file_io.py`](/code/stable/tensorflow/python/lib/io/file_io.py).

Rename or move a file / directory.

#### Args:

* <b>`src`</b>: string, pathname for a file
* <b>`dst`</b>: string, pathname to which the file needs to be moved
* <b>`overwrite`</b>: boolean, if false it's an error for `dst` to be occupied by an
    existing file.


#### Raises:

* <b>`errors.OpError`</b>: If the operation fails.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.gfile.MakeDirs" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.gfile.MakeDirs

Creates a directory and all parent/intermediate directories.

``` python
tf.compat.v1.gfile.MakeDirs(dirname)
```



Defined in [`python/lib/io/file_io.py`](/code/stable/tensorflow/python/lib/io/file_io.py).

<!-- Placeholder for "Used in" -->

It succeeds if dirname already exists and is writable.

#### Args:


* <b>`dirname`</b>: string, name of the directory to be created


#### Raises:


* <b>`errors.OpError`</b>: If the operation fails.
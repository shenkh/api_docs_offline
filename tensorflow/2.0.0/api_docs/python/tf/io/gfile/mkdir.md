<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.gfile.mkdir" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.gfile.mkdir

``` python
tf.io.gfile.mkdir(path)
```



Defined in [`tensorflow/python/lib/io/file_io.py`](/code/stable/tensorflow/python/lib/io/file_io.py).

Creates a directory with the name given by 'path'.

#### Args:

* <b>`path`</b>: string, name of the directory to be created
Notes: The parent directories need to exist. Use recursive_create_dir instead
  if there is the possibility that the parent dirs don't exist.


#### Raises:

* <b>`errors.OpError`</b>: If the operation fails.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.gfile.Glob" />
<meta itemprop="path" content="Stable" />
</div>

# tf.gfile.Glob

``` python
tf.gfile.Glob(filename)
```



Defined in [`tensorflow/python/lib/io/file_io.py`](/code/stable/tensorflow/python/lib/io/file_io.py).

Returns a list of files that match the given pattern(s).

#### Args:

* <b>`filename`</b>: string or iterable of strings. The glob pattern(s).


#### Returns:

A list of strings containing filenames that match the given pattern(s).


#### Raises:

* <b>`errors.OpError`</b>: If there are filesystem / directory listing errors.
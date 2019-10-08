<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.gfile.glob" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.gfile.glob

``` python
tf.io.gfile.glob(pattern)
```



Defined in [`tensorflow/python/lib/io/file_io.py`](/code/stable/tensorflow/python/lib/io/file_io.py).

Returns a list of files that match the given pattern(s).

#### Args:

* <b>`pattern`</b>: string or iterable of strings. The glob pattern(s).


#### Returns:

A list of strings containing filenames that match the given pattern(s).


#### Raises:

* <b>`errors.OpError`</b>: If there are filesystem / directory listing errors.
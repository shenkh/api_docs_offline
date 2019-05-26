<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.FileWriterCache" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="clear"/>
<meta itemprop="property" content="get"/>
</div>

# tf.summary.FileWriterCache

## Class `FileWriterCache`





Defined in [`tensorflow/python/summary/writer/writer_cache.py`](/code/stable/tensorflow/python/summary/writer/writer_cache.py).

Cache for file writers.

This class caches file writers, one per directory.

## Methods

<h3 id="clear"><code>clear</code></h3>

``` python
@staticmethod
clear()
```

Clear cached summary writers. Currently only used for unit tests.

<h3 id="get"><code>get</code></h3>

``` python
@staticmethod
get(logdir)
```

Returns the FileWriter for the specified directory.

#### Args:

* <b>`logdir`</b>: str, name of the directory.


#### Returns:

A `FileWriter`.




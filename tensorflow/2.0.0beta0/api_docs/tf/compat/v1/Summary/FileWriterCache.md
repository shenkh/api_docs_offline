<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.summary.FileWriterCache" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="clear"/>
<meta itemprop="property" content="get"/>
</div>

# tf.compat.v1.summary.FileWriterCache

## Class `FileWriterCache`

Cache for file writers.





Defined in [`python/summary/writer/writer_cache.py`](/code/stable/tensorflow/python/summary/writer/writer_cache.py).

<!-- Placeholder for "Used in" -->

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





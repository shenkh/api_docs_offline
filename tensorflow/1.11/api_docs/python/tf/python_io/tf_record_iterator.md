<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.python_io.tf_record_iterator" />
<meta itemprop="path" content="Stable" />
</div>

# tf.python_io.tf_record_iterator

``` python
tf.python_io.tf_record_iterator(
    path,
    options=None
)
```



Defined in [`tensorflow/python/lib/io/tf_record.py`](https://www.tensorflow.org/code/tensorflow/python/lib/io/tf_record.py).

An iterator that read the records from a TFRecords file.

#### Args:

* <b>`path`</b>: The path to the TFRecords file.
* <b>`options`</b>: (optional) A TFRecordOptions object.


#### Yields:

Strings.


#### Raises:

* <b>`IOError`</b>: If `path` cannot be opened for reading.
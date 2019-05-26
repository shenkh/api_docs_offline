<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.tf_record_iterator" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.tf_record_iterator

### Aliases:

* `tf.io.tf_record_iterator`
* `tf.python_io.tf_record_iterator`

``` python
tf.io.tf_record_iterator(
    path,
    options=None
)
```



Defined in [`tensorflow/python/lib/io/tf_record.py`](/code/stable/tensorflow/python/lib/io/tf_record.py).

An iterator that read the records from a TFRecords file.

#### Args:

* <b>`path`</b>: The path to the TFRecords file.
* <b>`options`</b>: (optional) A TFRecordOptions object.


#### Yields:

Strings.


#### Raises:

* <b>`IOError`</b>: If `path` cannot be opened for reading.
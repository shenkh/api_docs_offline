<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.TFRecordOptions" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_compression_type_string"/>
<meta itemprop="property" content="compression_type_map"/>
</div>

# tf.io.TFRecordOptions

## Class `TFRecordOptions`





Defined in [`tensorflow/python/lib/io/tf_record.py`](/code/stable/tensorflow/python/lib/io/tf_record.py).

Options used for manipulating TFRecord files.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    compression_type=None,
    flush_mode=None,
    input_buffer_size=None,
    output_buffer_size=None,
    window_bits=None,
    compression_level=None,
    compression_method=None,
    mem_level=None,
    compression_strategy=None
)
```

Creates a `TFRecordOptions` instance.

Options only effect TFRecordWriter when compression_type is not `None`.
Documentation, details, and defaults can be found in
[`zlib_compression_options.h`](https://www.tensorflow.org/code/tensorflow/core/lib/io/zlib_compression_options.h)
and in the [zlib manual](http://www.zlib.net/manual.html).
Leaving an option as `None` allows C++ to set a reasonable default.

#### Args:

* <b>`compression_type`</b>: `"GZIP"`, `"ZLIB"`, or `""` (no compression).
* <b>`flush_mode`</b>: flush mode or `None`, Default: Z_NO_FLUSH.
* <b>`input_buffer_size`</b>: int or `None`.
* <b>`output_buffer_size`</b>: int or `None`.
* <b>`window_bits`</b>: int or `None`.
* <b>`compression_level`</b>: 0 to 9, or `None`.
* <b>`compression_method`</b>: compression method or `None`.
* <b>`mem_level`</b>: 1 to 9, or `None`.
* <b>`compression_strategy`</b>: strategy or `None`. Default: Z_DEFAULT_STRATEGY.


#### Returns:

A `TFRecordOptions` object.


#### Raises:

* <b>`ValueError`</b>: If compression_type is invalid.



## Methods

<h3 id="get_compression_type_string"><code>get_compression_type_string</code></h3>

``` python
@classmethod
get_compression_type_string(
    cls,
    options
)
```

Convert various option types to a unified string.

#### Args:

* <b>`options`</b>: `TFRecordOption`, `TFRecordCompressionType`, or string.


#### Returns:

Compression type as string (e.g. `'ZLIB'`, `'GZIP'`, or `''`).


#### Raises:

* <b>`ValueError`</b>: If compression_type is invalid.



## Class Members

<h3 id="compression_type_map"><code>compression_type_map</code></h3>


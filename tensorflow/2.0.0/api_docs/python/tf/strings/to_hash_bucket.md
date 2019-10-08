<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.to_hash_bucket" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.to_hash_bucket

``` python
tf.strings.to_hash_bucket(
    input,
    num_buckets,
    name=None
)
```



Defined in [`tensorflow/python/ops/string_ops.py`](/code/stable/tensorflow/python/ops/string_ops.py).

Converts each string in the input Tensor to its hash mod by a number of buckets.

The hash function is deterministic on the content of the string within the
process.

Note that the hash function may change from time to time.
This functionality will be deprecated and it's recommended to use
`tf.strings.to_hash_bucket_fast()` or `tf.strings.to_hash_bucket_strong()`.

#### Args:

* <b>`input`</b>: A `Tensor` of type `string`.
* <b>`num_buckets`</b>: An `int` that is `>= 1`. The number of buckets.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `int64`.
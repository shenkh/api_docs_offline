<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.to_hash_bucket" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.to_hash_bucket

### Aliases:

* `tf.string_to_hash_bucket`
* `tf.strings.to_hash_bucket`

``` python
tf.strings.to_hash_bucket(
    string_tensor,
    num_buckets,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_string_ops.py`.

Converts each string in the input Tensor to its hash mod by a number of buckets.

The hash function is deterministic on the content of the string within the
process.

Note that the hash function may change from time to time.
This functionality will be deprecated and it's recommended to use
`tf.string_to_hash_bucket_fast()` or `tf.string_to_hash_bucket_strong()`.

#### Args:

* <b>`string_tensor`</b>: A `Tensor` of type `string`.
* <b>`num_buckets`</b>: An `int` that is `>= 1`. The number of buckets.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `int64`.
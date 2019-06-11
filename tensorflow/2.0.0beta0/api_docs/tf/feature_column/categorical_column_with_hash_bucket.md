<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.feature_column.categorical_column_with_hash_bucket" />
<meta itemprop="path" content="Stable" />
</div>

# tf.feature_column.categorical_column_with_hash_bucket

Represents sparse feature where ids are set by hashing.

### Aliases:

* `tf.compat.v1.feature_column.categorical_column_with_hash_bucket`
* `tf.compat.v2.feature_column.categorical_column_with_hash_bucket`
* `tf.feature_column.categorical_column_with_hash_bucket`

``` python
tf.feature_column.categorical_column_with_hash_bucket(
    key,
    hash_bucket_size,
    dtype=tf.dtypes.string
)
```



Defined in [`python/feature_column/feature_column_v2.py`](/code/stable/tensorflow/python/feature_column/feature_column_v2.py).

<!-- Placeholder for "Used in" -->

Use this when your sparse features are in string or integer format, and you
want to distribute your inputs into a finite number of buckets by hashing.
output_id = Hash(input_feature_string) % bucket_size for string type input.
For int type input, the value is converted to its string representation first
and then hashed by the same formula.

For input dictionary `features`, `features[key]` is either `Tensor` or
`SparseTensor`. If `Tensor`, missing values can be represented by `-1` for int
and `''` for string, which will be dropped by this feature column.

#### Example:



```python
keywords = categorical_column_with_hash_bucket("keywords", 10K)
columns = [keywords, ...]
features = tf.io.parse_example(..., features=make_parse_example_spec(columns))
linear_prediction = linear_model(features, columns)

# or
keywords_embedded = embedding_column(keywords, 16)
columns = [keywords_embedded, ...]
features = tf.io.parse_example(..., features=make_parse_example_spec(columns))
dense_tensor = input_layer(features, columns)
```

#### Args:


* <b>`key`</b>: A unique string identifying the input feature. It is used as the
  column name and the dictionary key for feature parsing configs, feature
  `Tensor` objects, and feature columns.
* <b>`hash_bucket_size`</b>: An int > 1. The number of buckets.
* <b>`dtype`</b>: The type of features. Only string and integer types are supported.


#### Returns:

A `HashedCategoricalColumn`.



#### Raises:


* <b>`ValueError`</b>: `hash_bucket_size` is not greater than 1.
* <b>`ValueError`</b>: `dtype` is neither string nor integer.
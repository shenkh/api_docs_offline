<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.feature_column.sequence_categorical_column_with_identity" />
<meta itemprop="path" content="Stable" />
</div>

# tf.feature_column.sequence_categorical_column_with_identity

``` python
tf.feature_column.sequence_categorical_column_with_identity(
    key,
    num_buckets,
    default_value=None
)
```



Defined in [`tensorflow/python/feature_column/sequence_feature_column.py`](/code/stable/tensorflow/python/feature_column/sequence_feature_column.py).

Returns a feature column that represents sequences of integers.

Pass this to `embedding_column` or `indicator_column` to convert sequence
categorical data into dense representation for input to sequence NN, such as
RNN.

Example:

```python
watches = sequence_categorical_column_with_identity(
    'watches', num_buckets=1000)
watches_embedding = embedding_column(watches, dimension=10)
columns = [watches_embedding]

features = tf.io.parse_example(..., features=make_parse_example_spec(columns))
sequence_feature_layer = SequenceFeatures(columns)
sequence_input, sequence_length = sequence_feature_layer(features)
sequence_length_mask = tf.sequence_mask(sequence_length)

rnn_cell = tf.keras.layers.SimpleRNNCell(hidden_size)
rnn_layer = tf.keras.layers.RNN(rnn_cell)
outputs, state = rnn_layer(sequence_input, mask=sequence_length_mask)
```

#### Args:

* <b>`key`</b>: A unique string identifying the input feature.
* <b>`num_buckets`</b>: Range of inputs. Namely, inputs are expected to be in the
    range `[0, num_buckets)`.
* <b>`default_value`</b>: If `None`, this column's graph operations will fail for
    out-of-range inputs. Otherwise, this value must be in the range
    `[0, num_buckets)`, and will replace out-of-range inputs.


#### Returns:

A `SequenceCategoricalColumn`.


#### Raises:

* <b>`ValueError`</b>: if `num_buckets` is less than one.
* <b>`ValueError`</b>: if `default_value` is not in range `[0, num_buckets)`.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.export.build_raw_serving_input_receiver_fn" />
<meta itemprop="path" content="Stable" />
</div>

# tf.estimator.export.build_raw_serving_input_receiver_fn

``` python
tf.estimator.export.build_raw_serving_input_receiver_fn(
    features,
    default_batch_size=None
)
```

Build a serving_input_receiver_fn expecting feature Tensors.

Creates an serving_input_receiver_fn that expects all features to be fed
directly.

#### Args:

* <b>`features`</b>: a dict of string to `Tensor`.
* <b>`default_batch_size`</b>: the number of query examples expected per batch.
      Leave unset for variable batch size (recommended).


#### Returns:

A serving_input_receiver_fn.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.estimator.experimental.dnn_logit_fn_builder" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.estimator.experimental.dnn_logit_fn_builder

Function builder for a dnn logit_fn.

``` python
tf.compat.v1.estimator.experimental.dnn_logit_fn_builder(
    units,
    hidden_units,
    feature_columns,
    activation_fn,
    dropout,
    input_layer_partitioner,
    batch_norm
)
```



Defined in [`python/estimator/canned/dnn.py`](https://github.com/tensorflow/estimator/tree/master/tensorflow_estimator/python/estimator/canned/dnn.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`units`</b>: An int indicating the dimension of the logit layer.  In the
  MultiHead case, this should be the sum of all component Heads' logit
  dimensions.
* <b>`hidden_units`</b>: Iterable of integer number of hidden units per layer.
* <b>`feature_columns`</b>: Iterable of `feature_column._FeatureColumn` model inputs.
* <b>`activation_fn`</b>: Activation function applied to each layer.
* <b>`dropout`</b>: When not `None`, the probability we will drop out a given
  coordinate.
* <b>`input_layer_partitioner`</b>: Partitioner for input layer.
* <b>`batch_norm`</b>: Whether to use batch normalization after each hidden layer.


#### Returns:

A logit_fn (see below).



#### Raises:


* <b>`ValueError`</b>: If units is not an int.
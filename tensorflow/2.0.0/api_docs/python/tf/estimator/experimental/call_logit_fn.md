<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.experimental.call_logit_fn" />
<meta itemprop="path" content="Stable" />
</div>

# tf.estimator.experimental.call_logit_fn

``` python
tf.estimator.experimental.call_logit_fn(
    logit_fn,
    features,
    mode,
    params,
    config
)
```

Calls logit_fn (experimental).

THIS FUNCTION IS EXPERIMENTAL. Keras layers/models are the recommended APIs
for logit and model composition.

A utility function that calls the provided logit_fn with the relevant subset
of provided arguments. Similar to tf.estimator._call_model_fn().

#### Args:

* <b>`logit_fn`</b>: A logit_fn as defined above.
* <b>`features`</b>: The features dict.
* <b>`mode`</b>: TRAIN / EVAL / PREDICT ModeKeys.
* <b>`params`</b>: The hyperparameter dict.
* <b>`config`</b>: The configuration object.


#### Returns:

A logit Tensor, the output of logit_fn.


#### Raises:

* <b>`ValueError`</b>: if logit_fn does not return a Tensor or a dictionary mapping
    strings to Tensors.
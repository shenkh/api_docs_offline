<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.saved_model.regression_signature_def" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.saved_model.regression_signature_def

Creates regression signature from given examples and predictions.

### Aliases:

* `tf.compat.v1.saved_model.regression_signature_def`
* `tf.compat.v1.saved_model.signature_def_utils.regression_signature_def`

``` python
tf.compat.v1.saved_model.regression_signature_def(
    examples,
    predictions
)
```



Defined in [`python/saved_model/signature_def_utils_impl.py`](/code/stable/tensorflow/python/saved_model/signature_def_utils_impl.py).

<!-- Placeholder for "Used in" -->

This function produces signatures intended for use with the TensorFlow Serving
Regress API (tensorflow_serving/apis/prediction_service.proto), and so
constrains the input and output types to those allowed by TensorFlow Serving.

#### Args:


* <b>`examples`</b>: A string `Tensor`, expected to accept serialized tf.Examples.
* <b>`predictions`</b>: A float `Tensor`.


#### Returns:

A regression-flavored signature_def.



#### Raises:


* <b>`ValueError`</b>: If examples is `None`.
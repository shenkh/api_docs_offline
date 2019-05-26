<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.estimator.build_supervised_input_receiver_fn_from_input_fn" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.estimator.build_supervised_input_receiver_fn_from_input_fn

``` python
tf.contrib.estimator.build_supervised_input_receiver_fn_from_input_fn(
    input_fn,
    **input_fn_args
)
```



Defined in [`tensorflow/python/estimator/export/export.py`](/code/stable/tensorflow/python/estimator/export/export.py).

Get a function that returns a SupervisedInputReceiver matching an input_fn.

Note that this function calls the input_fn in a local graph in order to
extract features and labels. Placeholders are then created from those
features and labels in the default graph.

#### Args:

* <b>`input_fn`</b>: An Estimator input_fn, which is a function that returns one of:

    * A 'tf.data.Dataset' object: Outputs of `Dataset` object must be a
        tuple (features, labels) with same constraints as below.
    * A tuple (features, labels): Where `features` is a `Tensor` or a
      dictionary of string feature name to `Tensor` and `labels` is a
      `Tensor` or a dictionary of string label name to `Tensor`. Both
      `features` and `labels` are consumed by `model_fn`. They should
      satisfy the expectation of `model_fn` from inputs.

* <b>`**input_fn_args`</b>: set of kwargs to be passed to the input_fn. Note that
    these will not be checked or validated here, and any errors raised by
    the input_fn will be thrown to the top.


#### Returns:

A function taking no arguments that, when called, returns a
SupervisedInputReceiver. This function can be passed in as part of the
input_receiver_map when exporting SavedModels from Estimator with multiple
modes.
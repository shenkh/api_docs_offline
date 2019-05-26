<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.predictor.from_saved_model" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.predictor.from_saved_model

``` python
tf.contrib.predictor.from_saved_model(
    export_dir,
    signature_def_key=None,
    signature_def=None,
    input_names=None,
    output_names=None,
    tags=None,
    graph=None,
    config=None
)
```



Defined in [`tensorflow/contrib/predictor/predictor_factories.py`](https://www.tensorflow.org/code/tensorflow/contrib/predictor/predictor_factories.py).

Constructs a `Predictor` from a `SavedModel` on disk.

#### Args:

* <b>`export_dir`</b>: a path to a directory containing a `SavedModel`.
* <b>`signature_def_key`</b>: Optional string specifying the signature to use. If
    `None`, then `DEFAULT_SERVING_SIGNATURE_DEF_KEY` is used. Only one of
  `signature_def_key` and `signature_def`
* <b>`signature_def`</b>: A `SignatureDef` proto specifying the inputs and outputs
    for prediction. Only one of `signature_def_key` and `signature_def`
    should be specified.
* <b>`input_names`</b>: A dictionary mapping strings to `Tensor`s in the `SavedModel`
      that represent the input. The keys can be any string of the user's
      choosing.
* <b>`output_names`</b>: A dictionary mapping strings to `Tensor`s in the
      `SavedModel` that represent the output. The keys can be any string of
      the user's choosing.
* <b>`tags`</b>: Optional. Tags that will be used to retrieve the correct
    `SignatureDef`. Defaults to `DEFAULT_TAGS`.
* <b>`graph`</b>: Optional. The Tensorflow `graph` in which prediction should be
    done.
* <b>`config`</b>: `ConfigProto` proto used to configure the session.


#### Returns:

An initialized `Predictor`.


#### Raises:

* <b>`ValueError`</b>: More than one of `signature_def_key` and `signature_def` is
    specified.
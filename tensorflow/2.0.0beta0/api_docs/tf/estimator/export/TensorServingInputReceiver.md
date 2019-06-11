<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.export.TensorServingInputReceiver" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="features"/>
<meta itemprop="property" content="receiver_tensors"/>
<meta itemprop="property" content="receiver_tensors_alternatives"/>
</div>

# tf.estimator.export.TensorServingInputReceiver

## Class `TensorServingInputReceiver`

A return type for a serving_input_receiver_fn.



### Aliases:

* Class `tf.compat.v1.estimator.export.TensorServingInputReceiver`
* Class `tf.compat.v2.estimator.export.TensorServingInputReceiver`
* Class `tf.estimator.export.TensorServingInputReceiver`



Defined in [`python/estimator/export/export.py`](https://github.com/tensorflow/estimator/tree/master/tensorflow_estimator/python/estimator/export/export.py).

<!-- Placeholder for "Used in" -->

This is for use with models that expect a single `Tensor` or `SparseTensor`
as an input feature, as opposed to a dict of features.

The normal `ServingInputReceiver` always returns a feature dict, even if it
contains only one entry, and so can be used only with models that accept such
a dict.  For models that accept only a single raw feature, the
`serving_input_receiver_fn` provided to `Estimator.export_saved_model()`
should return this `TensorServingInputReceiver` instead.  See:
https://github.com/tensorflow/tensorflow/issues/11674

Note that the receiver_tensors and receiver_tensor_alternatives arguments
will be automatically converted to the dict representation in either case,
because the SavedModel format requires each input `Tensor` to have a name
(provided by the dict key).

The expected return values are:
  features: A single `Tensor` or `SparseTensor`, representing the feature
    to be passed to the model.
  receiver_tensors: A `Tensor`, `SparseTensor`, or dict of string to `Tensor`
    or `SparseTensor`, specifying input nodes where this receiver expects to
    be fed by default.  Typically, this is a single placeholder expecting
    serialized `tf.Example` protos.
  receiver_tensors_alternatives: a dict of string to additional
    groups of receiver tensors, each of which may be a `Tensor`,
    `SparseTensor`, or dict of string to `Tensor` or`SparseTensor`.
    These named receiver tensor alternatives generate additional serving
    signatures, which may be used to feed inputs at different points within
    the input receiver subgraph.  A typical usage is to allow feeding raw
    feature `Tensor`s *downstream* of the tf.parse_example() op.
    Defaults to None.

## Properties

<h3 id="features"><code>features</code></h3>




<h3 id="receiver_tensors"><code>receiver_tensors</code></h3>




<h3 id="receiver_tensors_alternatives"><code>receiver_tensors_alternatives</code></h3>







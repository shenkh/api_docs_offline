<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.export.RegressionOutput" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="value"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="as_signature_def"/>
</div>

# tf.estimator.export.RegressionOutput

## Class `RegressionOutput`

Represents the output of a regression head.

Inherits From: [`ExportOutput`](../../../tf/estimator/export/ExportOutput.md)

### Aliases:

* Class `tf.compat.v1.estimator.export.RegressionOutput`
* Class `tf.compat.v2.estimator.export.RegressionOutput`
* Class `tf.estimator.export.RegressionOutput`



Defined in [`python/saved_model/model_utils/export_output.py`](/code/stable/tensorflow/python/saved_model/model_utils/export_output.py).

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(value)
```

Constructor for `RegressionOutput`.


#### Args:


* <b>`value`</b>: a float `Tensor` giving the predicted values.  Required.


#### Raises:


* <b>`ValueError`</b>: if the value is not a `Tensor` with dtype tf.float32.



## Properties

<h3 id="value"><code>value</code></h3>






## Methods

<h3 id="as_signature_def"><code>as_signature_def</code></h3>

``` python
as_signature_def(receiver_tensors)
```

Generate a SignatureDef proto for inclusion in a MetaGraphDef.

The SignatureDef will specify outputs as described in this ExportOutput,
and will use the provided receiver_tensors as inputs.

#### Args:


* <b>`receiver_tensors`</b>: a `Tensor`, or a dict of string to `Tensor`, specifying
  input nodes that will be fed.




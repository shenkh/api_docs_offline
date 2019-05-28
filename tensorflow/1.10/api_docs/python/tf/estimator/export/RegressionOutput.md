<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.export.RegressionOutput" />
<meta itemprop="property" content="value"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="as_signature_def"/>
</div>

# tf.estimator.export.RegressionOutput

## Class `RegressionOutput`

Inherits From: [`ExportOutput`](../../../tf/estimator/export/ExportOutput.md)



Defined in [`tensorflow/python/estimator/export/export_output.py`](https://www.tensorflow.org/code/tensorflow/python/estimator/export/export_output.py).

Represents the output of a regression head.

## Properties

<h3 id="value"><code>value</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(value)
```

Constructor for `RegressionOutput`.

#### Args:

* <b>`value`</b>: a float `Tensor` giving the predicted values.  Required.


#### Raises:

* <b>`ValueError`</b>: if the value is not a `Tensor` with dtype tf.float32.

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




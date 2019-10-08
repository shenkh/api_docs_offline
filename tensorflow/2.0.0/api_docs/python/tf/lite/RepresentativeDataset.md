<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.lite.RepresentativeDataset" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.lite.RepresentativeDataset

## Class `RepresentativeDataset`





Defined in [`tensorflow/lite/python/lite.py`](/code/stable/tensorflow/lite/python/lite.py).

Representative dataset to evaluate optimizations.

A representative dataset that can be used to evaluate optimizations by the
converter. E.g. converter can use these examples to estimate (min, max) ranges
by calibrating the model on inputs. This can allow converter to quantize a
converted floating point model.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(input_gen)
```

Creates a representative dataset.

#### Args:

* <b>`input_gen`</b>: an input generator that can be used to generate input samples
    for the model. This must be a callable object that returns an object
    that supports the `iter()` protocol (e.g. a generator function). The
    elements generated must have same type and shape as inputs to the model.




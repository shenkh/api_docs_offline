<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.quantize.experimental_create_eval_graph" />
</div>

# tf.contrib.quantize.experimental_create_eval_graph

``` python
tf.contrib.quantize.experimental_create_eval_graph(
    input_graph=None,
    weight_bits=8,
    activation_bits=8,
    quant_delay=None,
    scope=None
)
```



Defined in [`tensorflow/contrib/quantize/python/quantize_graph.py`](https://www.tensorflow.org/code/tensorflow/contrib/quantize/python/quantize_graph.py).

Rewrites an eval input_graph in place for simulated quantization.

Variables added by the rewrite get added to the global variables collection.

This function has additional experimental options not (yet) available to
create_eval_graph. The resulting behavior may be undefined.

The graph has fake quantization ops inserted to simulate the error
introduced by quantization. Since the graph is transformed in place,
the expected behavior of previously held references to nodes and tensors may
change.

#### Args:

* <b>`input_graph`</b>: The tf.Graph to be transformed, if None then defaults to the
    default graph.
* <b>`weight_bits`</b>: Number of bits to use for quantizing weights.
* <b>`activation_bits`</b>: Number of bits to use for quantizing activations.
* <b>`quant_delay`</b>: Number of steps after which weights and activations are
    quantized during eval.
* <b>`scope`</b>: The scope to be transformed. If it's not None, only the ops which
    are in this scope will be transformed.


#### Raises:

* <b>`ValueError`</b>: If elements contains an element that isn't a tf.Tensor or
    tf.Operation.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.seq2seq.GreedyEmbeddingHelper" />
<meta itemprop="property" content="batch_size"/>
<meta itemprop="property" content="sample_ids_dtype"/>
<meta itemprop="property" content="sample_ids_shape"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="initialize"/>
<meta itemprop="property" content="next_inputs"/>
<meta itemprop="property" content="sample"/>
</div>

# tf.contrib.seq2seq.GreedyEmbeddingHelper

## Class `GreedyEmbeddingHelper`

Inherits From: [`Helper`](../../../tf/contrib/seq2seq/Helper.md)



Defined in [`tensorflow/contrib/seq2seq/python/ops/helper.py`](https://www.tensorflow.org/code/tensorflow/contrib/seq2seq/python/ops/helper.py).

See the guide: [Seq2seq Library (contrib) > Dynamic Decoding](../../../../../api_guides/python/contrib.seq2seq.md#Dynamic_Decoding)

A helper for use during inference.

Uses the argmax of the output (treated as logits) and passes the
result through an embedding layer to get the next input.

## Properties

<h3 id="batch_size"><code>batch_size</code></h3>

Batch size of tensor returned by `sample`.

Returns a scalar int32 tensor.

<h3 id="sample_ids_dtype"><code>sample_ids_dtype</code></h3>

DType of tensor returned by `sample`.

Returns a DType.

<h3 id="sample_ids_shape"><code>sample_ids_shape</code></h3>

Shape of tensor returned by `sample`, excluding the batch dimension.

Returns a `TensorShape`.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    embedding,
    start_tokens,
    end_token
)
```

Initializer.

#### Args:

* <b>`embedding`</b>: A callable that takes a vector tensor of `ids` (argmax ids),
    or the `params` argument for `embedding_lookup`. The returned tensor
    will be passed to the decoder input.
* <b>`start_tokens`</b>: `int32` vector shaped `[batch_size]`, the start tokens.
* <b>`end_token`</b>: `int32` scalar, the token that marks end of decoding.


#### Raises:

* <b>`ValueError`</b>: if `start_tokens` is not a 1D tensor or `end_token` is not a
    scalar.

<h3 id="initialize"><code>initialize</code></h3>

``` python
initialize(name=None)
```

Returns `(initial_finished, initial_inputs)`.

<h3 id="next_inputs"><code>next_inputs</code></h3>

``` python
next_inputs(
    time,
    outputs,
    state,
    sample_ids,
    name=None
)
```

next_inputs_fn for GreedyEmbeddingHelper.

<h3 id="sample"><code>sample</code></h3>

``` python
sample(
    time,
    outputs,
    state,
    name=None
)
```

sample for GreedyEmbeddingHelper.




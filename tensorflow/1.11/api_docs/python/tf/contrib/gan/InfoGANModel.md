<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.InfoGANModel" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="discriminator_and_aux_fn"/>
<meta itemprop="property" content="discriminator_fn"/>
<meta itemprop="property" content="discriminator_gen_outputs"/>
<meta itemprop="property" content="discriminator_real_outputs"/>
<meta itemprop="property" content="discriminator_scope"/>
<meta itemprop="property" content="discriminator_variables"/>
<meta itemprop="property" content="generated_data"/>
<meta itemprop="property" content="generator_fn"/>
<meta itemprop="property" content="generator_inputs"/>
<meta itemprop="property" content="generator_scope"/>
<meta itemprop="property" content="generator_variables"/>
<meta itemprop="property" content="predicted_distributions"/>
<meta itemprop="property" content="real_data"/>
<meta itemprop="property" content="structured_generator_inputs"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.contrib.gan.InfoGANModel

## Class `InfoGANModel`





Defined in [`tensorflow/contrib/gan/python/namedtuples.py`](https://www.tensorflow.org/code/tensorflow/contrib/gan/python/namedtuples.py).

An InfoGANModel contains all the pieces needed for InfoGAN training.

See https://arxiv.org/abs/1606.03657 for more details.

#### Args:

* <b>`structured_generator_inputs`</b>: A list of Tensors representing the random noise
    that must  have high mutual information with the generator output. List
    length should match `predicted_distributions`.
* <b>`predicted_distributions`</b>: A list of tf.Distributions. Predicted by the
    recognizer, and used to evaluate the likelihood of the structured noise.
    List length should match `structured_generator_inputs`.
* <b>`discriminator_and_aux_fn`</b>: The original discriminator function that returns
    a tuple of (logits, `predicted_distributions`).

<h2 id="__new__"><code>__new__</code></h2>

``` python
__new__(
    _cls,
    generator_inputs,
    generated_data,
    generator_variables,
    generator_scope,
    generator_fn,
    real_data,
    discriminator_real_outputs,
    discriminator_gen_outputs,
    discriminator_variables,
    discriminator_scope,
    discriminator_fn,
    structured_generator_inputs,
    predicted_distributions,
    discriminator_and_aux_fn
)
```

Create new instance of InfoGANModel(generator_inputs, generated_data, generator_variables, generator_scope, generator_fn, real_data, discriminator_real_outputs, discriminator_gen_outputs, discriminator_variables, discriminator_scope, discriminator_fn, structured_generator_inputs, predicted_distributions, discriminator_and_aux_fn)



## Properties

<h3 id="discriminator_and_aux_fn"><code>discriminator_and_aux_fn</code></h3>

Alias for field number 13

<h3 id="discriminator_fn"><code>discriminator_fn</code></h3>

Alias for field number 10

<h3 id="discriminator_gen_outputs"><code>discriminator_gen_outputs</code></h3>

Alias for field number 7

<h3 id="discriminator_real_outputs"><code>discriminator_real_outputs</code></h3>

Alias for field number 6

<h3 id="discriminator_scope"><code>discriminator_scope</code></h3>

Alias for field number 9

<h3 id="discriminator_variables"><code>discriminator_variables</code></h3>

Alias for field number 8

<h3 id="generated_data"><code>generated_data</code></h3>

Alias for field number 1

<h3 id="generator_fn"><code>generator_fn</code></h3>

Alias for field number 4

<h3 id="generator_inputs"><code>generator_inputs</code></h3>

Alias for field number 0

<h3 id="generator_scope"><code>generator_scope</code></h3>

Alias for field number 3

<h3 id="generator_variables"><code>generator_variables</code></h3>

Alias for field number 2

<h3 id="predicted_distributions"><code>predicted_distributions</code></h3>

Alias for field number 12

<h3 id="real_data"><code>real_data</code></h3>

Alias for field number 5

<h3 id="structured_generator_inputs"><code>structured_generator_inputs</code></h3>

Alias for field number 11




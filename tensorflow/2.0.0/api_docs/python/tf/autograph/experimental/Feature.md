<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.autograph.experimental.Feature" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="ALL"/>
<meta itemprop="property" content="ASSERT_STATEMENTS"/>
<meta itemprop="property" content="AUTO_CONTROL_DEPS"/>
<meta itemprop="property" content="BUILTIN_FUNCTIONS"/>
<meta itemprop="property" content="EQUALITY_OPERATORS"/>
<meta itemprop="property" content="LISTS"/>
<meta itemprop="property" content="NAME_SCOPES"/>
<meta itemprop="property" content="__members__"/>
</div>

# tf.autograph.experimental.Feature

## Class `Feature`





Defined in [`tensorflow/python/autograph/core/converter.py`](/code/stable/tensorflow/python/autograph/core/converter.py).

This enumeration represents optional conversion options.

These conversion options are experimental. They are subject to change without
notice and offer no guarantees.

_Example Usage_

```python
optionals= tf.autograph.experimental.Feature.EQUALITY_OPERATORS
@tf.function(experimental_autograph_options=optionals)
def f(i):
  if i == 0:  # EQUALITY_OPERATORS allows the use of == here.
    tf.print('i is zero')
```

#### Attributes:

* <b>`ALL`</b>: Enable all features.
* <b>`AUTO_CONTROL_DEPS`</b>: Insert of control dependencies in the generated code.
* <b>`ASSERT_STATEMENTS`</b>: Convert Tensor-dependent assert statements to tf.Assert.
* <b>`BUILTIN_FUNCTIONS`</b>: Convert builtin functions applied to Tensors to
    their TF counterparts.
* <b>`EQUALITY_OPERATORS`</b>: Whether to convert the comparison operators, like
    equality. This is soon to be deprecated as support is being added to the
    Tensor class.
* <b>`LISTS`</b>: Convert list idioms, like initializers, slices, append, etc.
* <b>`NAME_SCOPES`</b>: Insert name scopes that name ops according to context, like the
    function they were defined in.

## Class Members

<h3 id="ALL"><code>ALL</code></h3>

<h3 id="ASSERT_STATEMENTS"><code>ASSERT_STATEMENTS</code></h3>

<h3 id="AUTO_CONTROL_DEPS"><code>AUTO_CONTROL_DEPS</code></h3>

<h3 id="BUILTIN_FUNCTIONS"><code>BUILTIN_FUNCTIONS</code></h3>

<h3 id="EQUALITY_OPERATORS"><code>EQUALITY_OPERATORS</code></h3>

<h3 id="LISTS"><code>LISTS</code></h3>

<h3 id="NAME_SCOPES"><code>NAME_SCOPES</code></h3>

<h3 id="__members__"><code>__members__</code></h3>


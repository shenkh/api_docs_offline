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
</div>

# tf.autograph.experimental.Feature

## Class `Feature`

Represents conversion options that can be toggled on or off.



### Aliases:

* Class `tf.autograph.experimental.Feature`
* Class `tf.compat.v1.autograph.experimental.Feature`
* Class `tf.compat.v2.autograph.experimental.Feature`



Defined in [`python/autograph/core/converter.py`](/code/stable/tensorflow/python/autograph/core/converter.py).

<!-- Placeholder for "Used in" -->


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

* `ALL` <a id="ALL"></a>
* `ASSERT_STATEMENTS` <a id="ASSERT_STATEMENTS"></a>
* `AUTO_CONTROL_DEPS` <a id="AUTO_CONTROL_DEPS"></a>
* `BUILTIN_FUNCTIONS` <a id="BUILTIN_FUNCTIONS"></a>
* `EQUALITY_OPERATORS` <a id="EQUALITY_OPERATORS"></a>
* `LISTS` <a id="LISTS"></a>
* `NAME_SCOPES` <a id="NAME_SCOPES"></a>

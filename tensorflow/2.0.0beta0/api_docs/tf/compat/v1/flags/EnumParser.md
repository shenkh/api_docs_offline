<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.EnumParser" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="flag_type"/>
<meta itemprop="property" content="parse"/>
<meta itemprop="property" content="syntactic_help"/>
</div>

# tf.compat.v1.flags.EnumParser

## Class `EnumParser`

Parser of a string enum value (a string value from a given set).

Inherits From: [`ArgumentParser`](../../../../tf/compat/v1/flags/ArgumentParser.md)

### Aliases:

* Class `tf.compat.v1.app.flags.EnumParser`
* Class `tf.compat.v1.flags.EnumParser`

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    enum_values,
    case_sensitive=True
)
```

Initializes EnumParser.


#### Args:


* <b>`enum_values`</b>: [str], a non-empty list of string values in the enum.
* <b>`case_sensitive`</b>: bool, whether or not the enum is to be case-sensitive.


#### Raises:


* <b>`ValueError`</b>: When enum_values is empty.



## Methods

<h3 id="flag_type"><code>flag_type</code></h3>

``` python
flag_type()
```

See base class.


<h3 id="parse"><code>parse</code></h3>

``` python
parse(argument)
```

Determines validity of argument and returns the correct element of enum.


#### Args:


* <b>`argument`</b>: str, the supplied flag value.


#### Returns:

The first matching element from enum_values.



#### Raises:


* <b>`ValueError`</b>: Raised when argument didn't match anything in enum.



## Class Members

* `syntactic_help = ''` <a id="syntactic_help"></a>

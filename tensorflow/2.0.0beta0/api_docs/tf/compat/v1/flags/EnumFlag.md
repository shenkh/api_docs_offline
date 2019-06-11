<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.EnumFlag" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="value"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__ge__"/>
<meta itemprop="property" content="__gt__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__le__"/>
<meta itemprop="property" content="__lt__"/>
<meta itemprop="property" content="flag_type"/>
<meta itemprop="property" content="parse"/>
<meta itemprop="property" content="serialize"/>
<meta itemprop="property" content="unparse"/>
</div>

# tf.compat.v1.flags.EnumFlag

## Class `EnumFlag`

Basic enum flag; its value can be any string from list of enum_values.

Inherits From: [`Flag`](../../../../tf/compat/v1/flags/Flag.md)

### Aliases:

* Class `tf.compat.v1.app.flags.EnumFlag`
* Class `tf.compat.v1.flags.EnumFlag`

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    name,
    default,
    help,
    enum_values,
    short_name=None,
    case_sensitive=True,
    **args
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Properties

<h3 id="value"><code>value</code></h3>






## Methods

<h3 id="__eq__"><code>__eq__</code></h3>

``` python
__eq__(other)
```

Return self==value.


<h3 id="__ge__"><code>__ge__</code></h3>

``` python
__ge__(
    other,
    NotImplemented=NotImplemented
)
```

Return a >= b.  Computed by @total_ordering from (not a < b).


<h3 id="__gt__"><code>__gt__</code></h3>

``` python
__gt__(
    other,
    NotImplemented=NotImplemented
)
```

Return a > b.  Computed by @total_ordering from (not a < b) and (a != b).


<h3 id="__le__"><code>__le__</code></h3>

``` python
__le__(
    other,
    NotImplemented=NotImplemented
)
```

Return a <= b.  Computed by @total_ordering from (a < b) or (a == b).


<h3 id="__lt__"><code>__lt__</code></h3>

``` python
__lt__(other)
```

Return self<value.


<h3 id="flag_type"><code>flag_type</code></h3>

``` python
flag_type()
```

Returns a str that describes the type of the flag.

NOTE: we use strings, and not the types.*Type constants because
our flags can have more exotic types, e.g., 'comma separated list
of strings', 'whitespace separated list of strings', etc.

<h3 id="parse"><code>parse</code></h3>

``` python
parse(argument)
```

Parses string and sets flag value.


#### Args:


* <b>`argument`</b>: str or the correct flag value type, argument to be parsed.

<h3 id="serialize"><code>serialize</code></h3>

``` python
serialize()
```




<h3 id="unparse"><code>unparse</code></h3>

``` python
unparse()
```







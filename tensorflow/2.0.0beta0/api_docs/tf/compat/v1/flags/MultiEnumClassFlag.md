<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.MultiEnumClassFlag" />
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

# tf.compat.v1.flags.MultiEnumClassFlag

## Class `MultiEnumClassFlag`

A multi_enum_class flag.

Inherits From: [`MultiFlag`](../../../../tf/compat/v1/flags/MultiFlag.md)

### Aliases:

* Class `tf.compat.v1.app.flags.MultiEnumClassFlag`
* Class `tf.compat.v1.flags.MultiEnumClassFlag`

<!-- Placeholder for "Used in" -->

See the __doc__ for MultiFlag for most behaviors of this class.  In addition,
this class knows how to handle enum.Enum instances as values for this flag
type.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    name,
    default,
    help_string,
    enum_class,
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

See base class.


<h3 id="parse"><code>parse</code></h3>

``` python
parse(arguments)
```

Parses one or more arguments with the installed parser.


#### Args:


* <b>`arguments`</b>: a single argument or a list of arguments (typically a
  list of default values); a single argument is converted
  internally into a list containing one item.

<h3 id="serialize"><code>serialize</code></h3>

``` python
serialize()
```

See base class.


<h3 id="unparse"><code>unparse</code></h3>

``` python
unparse()
```







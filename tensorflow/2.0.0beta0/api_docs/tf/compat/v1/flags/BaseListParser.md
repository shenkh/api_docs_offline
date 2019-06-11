<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.BaseListParser" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="flag_type"/>
<meta itemprop="property" content="parse"/>
<meta itemprop="property" content="syntactic_help"/>
</div>

# tf.compat.v1.flags.BaseListParser

## Class `BaseListParser`

Base class for a parser of lists of strings.

Inherits From: [`ArgumentParser`](../../../../tf/compat/v1/flags/ArgumentParser.md)

### Aliases:

* Class `tf.compat.v1.app.flags.BaseListParser`
* Class `tf.compat.v1.flags.BaseListParser`

<!-- Placeholder for "Used in" -->

To extend, inherit from this class; from the subclass __init__, call

    BaseListParser.__init__(self, token, name)

where token is a character used to tokenize, and name is a description
of the separator.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    token=None,
    name=None
)
```

Initialize self.  See help(type(self)) for accurate signature.




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

See base class.




## Class Members

* `syntactic_help = ''` <a id="syntactic_help"></a>

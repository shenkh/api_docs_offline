<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.WhitespaceSeparatedListParser" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="flag_type"/>
<meta itemprop="property" content="parse"/>
<meta itemprop="property" content="syntactic_help"/>
</div>

# tf.compat.v1.flags.WhitespaceSeparatedListParser

## Class `WhitespaceSeparatedListParser`

Parser for a whitespace-separated list of strings.

Inherits From: [`BaseListParser`](../../../../tf/compat/v1/flags/BaseListParser.md)

### Aliases:

* Class `tf.compat.v1.app.flags.WhitespaceSeparatedListParser`
* Class `tf.compat.v1.flags.WhitespaceSeparatedListParser`

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(comma_compat=False)
```

Initializer.


#### Args:


* <b>`comma_compat`</b>: bool, whether to support comma as an additional separator.
    If False then only whitespace is supported.  This is intended only for
    backwards compatibility with flags that used to be comma-separated.



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

Parses argument as whitespace-separated list of strings.

It also parses argument as comma-separated list of strings if requested.

#### Args:


* <b>`argument`</b>: string argument passed in the commandline.


#### Returns:

[str], the parsed flag value.




## Class Members

* `syntactic_help = ''` <a id="syntactic_help"></a>

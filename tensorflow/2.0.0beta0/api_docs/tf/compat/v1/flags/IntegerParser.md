<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.IntegerParser" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="convert"/>
<meta itemprop="property" content="flag_type"/>
<meta itemprop="property" content="is_outside_bounds"/>
<meta itemprop="property" content="parse"/>
<meta itemprop="property" content="number_article"/>
<meta itemprop="property" content="number_name"/>
<meta itemprop="property" content="syntactic_help"/>
</div>

# tf.compat.v1.flags.IntegerParser

## Class `IntegerParser`

Parser of an integer value.



### Aliases:

* Class `tf.compat.v1.app.flags.IntegerParser`
* Class `tf.compat.v1.flags.IntegerParser`

<!-- Placeholder for "Used in" -->

Parsed value may be bounded to a given upper and lower bound.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    lower_bound=None,
    upper_bound=None
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="convert"><code>convert</code></h3>

``` python
convert(argument)
```

Returns the int value of argument.


<h3 id="flag_type"><code>flag_type</code></h3>

``` python
flag_type()
```

See base class.


<h3 id="is_outside_bounds"><code>is_outside_bounds</code></h3>

``` python
is_outside_bounds(val)
```

Returns whether the value is outside the bounds or not.


<h3 id="parse"><code>parse</code></h3>

``` python
parse(argument)
```

See base class.




## Class Members

* `number_article = 'an'` <a id="number_article"></a>
* `number_name = 'integer'` <a id="number_name"></a>
* `syntactic_help = 'an integer'` <a id="syntactic_help"></a>

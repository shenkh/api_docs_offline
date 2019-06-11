<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.FloatParser" />
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

# tf.compat.v1.flags.FloatParser

## Class `FloatParser`

Parser of floating point values.



### Aliases:

* Class `tf.compat.v1.app.flags.FloatParser`
* Class `tf.compat.v1.flags.FloatParser`

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

Returns the float value of argument.


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

* `number_article = 'a'` <a id="number_article"></a>
* `number_name = 'number'` <a id="number_name"></a>
* `syntactic_help = 'a number'` <a id="syntactic_help"></a>

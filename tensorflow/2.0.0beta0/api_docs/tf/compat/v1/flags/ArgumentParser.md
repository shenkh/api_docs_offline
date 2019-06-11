<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.ArgumentParser" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="flag_type"/>
<meta itemprop="property" content="parse"/>
<meta itemprop="property" content="syntactic_help"/>
</div>

# tf.compat.v1.flags.ArgumentParser

## Class `ArgumentParser`

Base class used to parse and convert arguments.



### Aliases:

* Class `tf.compat.v1.app.flags.ArgumentParser`
* Class `tf.compat.v1.flags.ArgumentParser`

<!-- Placeholder for "Used in" -->

The parse() method checks to make sure that the string argument is a
legal value and convert it to a native type.  If the value cannot be
converted, it should throw a 'ValueError' exception with a human
readable explanation of why the value is illegal.

Subclasses should also define a syntactic_help string which may be
presented to the user to describe the form of the legal values.

Argument parser classes must be stateless, since instances are cached
and shared between flags. Initializer arguments are allowed, but all
member variables must be derived from initializer arguments only.

## Methods

<h3 id="flag_type"><code>flag_type</code></h3>

``` python
flag_type()
```

Returns a string representing the type of the flag.


<h3 id="parse"><code>parse</code></h3>

``` python
parse(argument)
```

Parses the string argument and returns the native value.

By default it returns its argument unmodified.

#### Args:


* <b>`argument`</b>: string argument passed in the commandline.


#### Raises:


* <b>`ValueError`</b>: Raised when it fails to parse the argument.
* <b>`TypeError`</b>: Raised when the argument has the wrong type.


#### Returns:

The parsed value in native type.




## Class Members

* `syntactic_help = ''` <a id="syntactic_help"></a>

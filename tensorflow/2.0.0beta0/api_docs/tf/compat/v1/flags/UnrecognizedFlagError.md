<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.UnrecognizedFlagError" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.compat.v1.flags.UnrecognizedFlagError

## Class `UnrecognizedFlagError`

Raised when a flag is unrecognized.

Inherits From: [`Error`](../../../../tf/compat/v1/flags/Error.md)

### Aliases:

* Class `tf.compat.v1.app.flags.UnrecognizedFlagError`
* Class `tf.compat.v1.flags.UnrecognizedFlagError`

<!-- Placeholder for "Used in" -->


#### Attributes:


* <b>`flagname`</b>: str, the name of the unrecognized flag.
* <b>`flagvalue`</b>: The value of the flag, empty if the flag is not defined.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    flagname,
    flagvalue='',
    suggestions=None
)
```

Initialize self.  See help(type(self)) for accurate signature.





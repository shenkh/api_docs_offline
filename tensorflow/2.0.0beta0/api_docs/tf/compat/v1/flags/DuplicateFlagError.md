<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.DuplicateFlagError" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="from_flag"/>
</div>

# tf.compat.v1.flags.DuplicateFlagError

## Class `DuplicateFlagError`

Raised if there is a flag naming conflict.

Inherits From: [`Error`](../../../../tf/compat/v1/flags/Error.md)

### Aliases:

* Class `tf.compat.v1.app.flags.DuplicateFlagError`
* Class `tf.compat.v1.flags.DuplicateFlagError`

<!-- Placeholder for "Used in" -->


## Methods

<h3 id="from_flag"><code>from_flag</code></h3>

``` python
@classmethod
from_flag(
    cls,
    flagname,
    flag_values,
    other_flag_values=None
)
```

Creates a DuplicateFlagError by providing flag name and values.


#### Args:


* <b>`flagname`</b>: str, the name of the flag being redefined.
* <b>`flag_values`</b>: FlagValues, the FlagValues instance containing the first
    definition of flagname.
* <b>`other_flag_values`</b>: FlagValues, if it is not None, it should be the
    FlagValues object where the second definition of flagname occurs.
    If it is None, we assume that we're being called when attempting
    to create the flag a second time, and we use the module calling
    this one as the source of the second definition.


#### Returns:

An instance of DuplicateFlagError.





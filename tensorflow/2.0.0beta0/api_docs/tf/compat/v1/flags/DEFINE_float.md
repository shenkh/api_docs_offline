<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.DEFINE_float" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.flags.DEFINE_float

Registers a flag whose value must be a float.

### Aliases:

* `tf.compat.v1.app.flags.DEFINE_float`
* `tf.compat.v1.flags.DEFINE_float`

``` python
tf.compat.v1.flags.DEFINE_float(
    name,
    default,
    help,
    lower_bound=None,
    upper_bound=None,
    flag_values=_flagvalues.FLAGS,
    **args
)
```

<!-- Placeholder for "Used in" -->

If lower_bound or upper_bound are set, then this flag must be
within the given range.

#### Args:


* <b>`name`</b>: str, the flag name.
* <b>`default`</b>: float|str|None, the default value of the flag.
* <b>`help`</b>: str, the help message.
* <b>`lower_bound`</b>: float, min value of the flag.
* <b>`upper_bound`</b>: float, max value of the flag.
* <b>`flag_values`</b>: FlagValues, the FlagValues instance with which the flag will
    be registered. This should almost never need to be overridden.
* <b>`**args`</b>: dict, the extra keyword args that are passed to DEFINE.
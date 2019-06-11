<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.DEFINE_enum" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.flags.DEFINE_enum

Registers a flag whose value can be any string from enum_values.

### Aliases:

* `tf.compat.v1.app.flags.DEFINE_enum`
* `tf.compat.v1.flags.DEFINE_enum`

``` python
tf.compat.v1.flags.DEFINE_enum(
    name,
    default,
    enum_values,
    help,
    flag_values=_flagvalues.FLAGS,
    module_name=None,
    **args
)
```

<!-- Placeholder for "Used in" -->

Instead of a string enum, prefer `DEFINE_enum_class`, which allows
defining enums from an `enum.Enum` class.

#### Args:


* <b>`name`</b>: str, the flag name.
* <b>`default`</b>: str|None, the default value of the flag.
* <b>`enum_values`</b>: [str], a non-empty list of strings with the possible values for
    the flag.
* <b>`help`</b>: str, the help message.
* <b>`flag_values`</b>: FlagValues, the FlagValues instance with which the flag will
    be registered. This should almost never need to be overridden.
* <b>`module_name`</b>: str, the name of the Python module declaring this flag.
    If not provided, it will be computed using the stack trace of this call.
* <b>`**args`</b>: dict, the extra keyword args that are passed to Flag __init__.
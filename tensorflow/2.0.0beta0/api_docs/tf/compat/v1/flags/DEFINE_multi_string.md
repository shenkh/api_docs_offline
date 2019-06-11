<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.DEFINE_multi_string" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.flags.DEFINE_multi_string

Registers a flag whose value can be a list of any strings.

### Aliases:

* `tf.compat.v1.app.flags.DEFINE_multi_string`
* `tf.compat.v1.flags.DEFINE_multi_string`

``` python
tf.compat.v1.flags.DEFINE_multi_string(
    name,
    default,
    help,
    flag_values=_flagvalues.FLAGS,
    **args
)
```

<!-- Placeholder for "Used in" -->

Use the flag on the command line multiple times to place multiple
string values into the list.  The 'default' may be a single string
(which will be converted into a single-element list) or a list of
strings.


#### Args:


* <b>`name`</b>: str, the flag name.
* <b>`default`</b>: Union[Iterable[Text], Text, None], the default value of the flag;
    see `DEFINE_multi`.
* <b>`help`</b>: str, the help message.
* <b>`flag_values`</b>: FlagValues, the FlagValues instance with which the flag will
    be registered. This should almost never need to be overridden.
* <b>`**args`</b>: Dictionary with extra keyword args that are passed to the
    Flag __init__.
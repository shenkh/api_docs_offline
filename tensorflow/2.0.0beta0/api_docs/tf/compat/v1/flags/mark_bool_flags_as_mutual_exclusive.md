<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.mark_bool_flags_as_mutual_exclusive" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.flags.mark_bool_flags_as_mutual_exclusive

Ensures that only one flag among flag_names is True.

### Aliases:

* `tf.compat.v1.app.flags.mark_bool_flags_as_mutual_exclusive`
* `tf.compat.v1.flags.mark_bool_flags_as_mutual_exclusive`

``` python
tf.compat.v1.flags.mark_bool_flags_as_mutual_exclusive(
    flag_names,
    required=False,
    flag_values=_flagvalues.FLAGS
)
```

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`flag_names`</b>: [str], names of the flags.
* <b>`required`</b>: bool. If true, exactly one flag must be True. Otherwise, at most
    one flag can be True, and it is valid for all flags to be False.
* <b>`flag_values`</b>: flags.FlagValues, optional FlagValues instance where the flags
    are defined.
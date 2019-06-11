<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.mark_flags_as_required" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.flags.mark_flags_as_required

Ensures that flags are not None during program execution.

### Aliases:

* `tf.compat.v1.app.flags.mark_flags_as_required`
* `tf.compat.v1.flags.mark_flags_as_required`

``` python
tf.compat.v1.flags.mark_flags_as_required(
    flag_names,
    flag_values=_flagvalues.FLAGS
)
```

<!-- Placeholder for "Used in" -->


#### Recommended usage:


if __name__ == '__main__':
  flags.mark_flags_as_required(['flag1', 'flag2', 'flag3'])
  app.run()



#### Args:


* <b>`flag_names`</b>: Sequence[str], names of the flags.
* <b>`flag_values`</b>: flags.FlagValues, optional FlagValues instance where the flags
    are defined.

#### Raises:


* <b>`AttributeError`</b>: If any of flag name has not already been defined as a flag.
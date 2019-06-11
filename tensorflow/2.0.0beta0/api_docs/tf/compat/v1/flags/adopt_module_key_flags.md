<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.adopt_module_key_flags" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.flags.adopt_module_key_flags

Declares that all flags key to a module are key to the current module.

### Aliases:

* `tf.compat.v1.app.flags.adopt_module_key_flags`
* `tf.compat.v1.flags.adopt_module_key_flags`

``` python
tf.compat.v1.flags.adopt_module_key_flags(
    module,
    flag_values=_flagvalues.FLAGS
)
```

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`module`</b>: module, the module object from which all key flags will be declared
    as key flags to the current module.
* <b>`flag_values`</b>: FlagValues, the FlagValues instance in which the flags will
    be declared as key flags. This should almost never need to be
    overridden.


#### Raises:


* <b>`Error`</b>: Raised when given an argument that is a module name (a string),
    instead of a module object.
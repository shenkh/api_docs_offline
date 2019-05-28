<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.eager.seterr" />
</div>

# tf.contrib.eager.seterr

``` python
tf.contrib.eager.seterr(inf_or_nan=None)
```



Defined in [`tensorflow/python/eager/execution_callbacks.py`](https://www.tensorflow.org/code/tensorflow/python/eager/execution_callbacks.py).

Set how abnormal conditions are handled by the default eager context.

Example:
```python
tfe.seterr(inf_or_nan="raise")
a = tf.constant(10.0)
b = tf.constant(0.0)
try:
  c = a / b  # <-- Raises InfOrNanError.
except Exception as e:
  print("Caught Exception: %s" % e)

tfe.seterr(inf_or_nan="ignore")
c = a / b  # <-- Does NOT raise exception anymore.
```

#### Args:

* <b>`inf_or_nan`</b>: Set action for infinity (`inf`) and NaN (`nan`) values.
    Possible values: `{"ignore", "print", "raise", "warn"}`.
    `"ignore"`: take no action when `inf` values appear.
    `"print"`: print a warning to `stdout`.
    `"raise"`: raise an `InfOrNanError`.
    `"warn"`: print a warning using <a href="../../../tf/logging/warn.md"><code>tf.logging.warn</code></a>.
    A value of `None` leads to no change in the action of the condition.


#### Returns:

A dictionary of old actions.


#### Raises:

* <b>`ValueError`</b>: If the value of any keyword arguments is invalid.
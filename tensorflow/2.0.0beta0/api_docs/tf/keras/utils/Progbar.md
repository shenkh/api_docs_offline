<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.Progbar" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="add"/>
<meta itemprop="property" content="update"/>
</div>

# tf.keras.utils.Progbar

## Class `Progbar`

Displays a progress bar.



### Aliases:

* Class `tf.compat.v1.keras.utils.Progbar`
* Class `tf.compat.v2.keras.utils.Progbar`
* Class `tf.keras.utils.Progbar`



Defined in [`python/keras/utils/generic_utils.py`](/code/stable/tensorflow/python/keras/utils/generic_utils.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`target`</b>: Total number of steps expected, None if unknown.
* <b>`width`</b>: Progress bar width on screen.
* <b>`verbose`</b>: Verbosity mode, 0 (silent), 1 (verbose), 2 (semi-verbose)
* <b>`stateful_metrics`</b>: Iterable of string names of metrics that
    should *not* be averaged over time. Metrics in this list
    will be displayed as-is. All others will be averaged
    by the progbar before display.
* <b>`interval`</b>: Minimum visual progress update interval (in seconds).
* <b>`unit_name`</b>: Display name for step counts (usually "step" or "sample").

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    target,
    width=30,
    verbose=1,
    interval=0.05,
    stateful_metrics=None,
    unit_name='step'
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="add"><code>add</code></h3>

``` python
add(
    n,
    values=None
)
```




<h3 id="update"><code>update</code></h3>

``` python
update(
    current,
    values=None
)
```

Updates the progress bar.


#### Arguments:


* <b>`current`</b>: Index of current step.
* <b>`values`</b>: List of tuples:
    `(name, value_for_last_step)`.
    If `name` is in `stateful_metrics`,
    `value_for_last_step` will be displayed as-is.
    Else, an average of the metric over time will be displayed.




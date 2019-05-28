<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute.TowerContext" />
<meta itemprop="property" content="device"/>
<meta itemprop="property" content="distribution_strategy"/>
<meta itemprop="property" content="is_single_tower"/>
<meta itemprop="property" content="num_towers"/>
<meta itemprop="property" content="tower_id"/>
<meta itemprop="property" content="__enter__"/>
<meta itemprop="property" content="__exit__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="merge_call"/>
</div>

# tf.contrib.distribute.TowerContext

## Class `TowerContext`





Defined in [`tensorflow/python/training/distribute.py`](https://www.tensorflow.org/code/tensorflow/python/training/distribute.py).

DistributionStrategy API inside a `call_for_each_tower()` call.

## Properties

<h3 id="device"><code>device</code></h3>

The device this tower is to be executed on, as a string.

<h3 id="distribution_strategy"><code>distribution_strategy</code></h3>

The current `DistributionStrategy` object.

<h3 id="is_single_tower"><code>is_single_tower</code></h3>

Returns whether there is a single tower or multiple.

<h3 id="num_towers"><code>num_towers</code></h3>

Returns number of towers, for purposes of averaging across towers.

<h3 id="tower_id"><code>tower_id</code></h3>

Which tower is being defined, a number from 0 to `num_towers - 1`.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    distribution_strategy,
    tower_id
)
```

Initialize self.  See help(type(self)) for accurate signature.

<h3 id="__enter__"><code>__enter__</code></h3>

``` python
__enter__()
```



<h3 id="__exit__"><code>__exit__</code></h3>

``` python
__exit__(
    exception_type,
    exception_value,
    traceback
)
```



<h3 id="merge_call"><code>merge_call</code></h3>

``` python
merge_call(
    merge_fn,
    *args,
    **kwargs
)
```

Merge args across towers and run `merge_fn` in a cross-tower context.

This allows communication and coordination when there are multiple calls
to a model function triggered by a call to
`distribution.call_for_each_tower(model_fn, ...)`.

See `MirroredDistribution.call_for_each_tower()` for an explanation.

Otherwise, this is equivalent to:

```
distribution = get_distribution_strategy()
with cross-tower-context(distribution):
  return merge_fn(distribution, *args, **kwargs)
```

#### Args:

* <b>`merge_fn`</b>: function that joins arguments from threads that are given as
    PerDevice. It accepts `DistributionStrategy` object as the first
    argument.
* <b>`*args`</b>: positional per-thread arguments for `merge_fn`
* <b>`**kwargs`</b>: keyword per-thread arguments for `merge_fn`.


#### Returns:

The return value of `merge_fn`, except for `PerDevice` values which are
unpacked.




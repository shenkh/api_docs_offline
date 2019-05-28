<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distribute.OneDeviceStrategy" />
<meta itemprop="property" content="is_single_tower"/>
<meta itemprop="property" content="num_towers"/>
<meta itemprop="property" content="parameter_devices"/>
<meta itemprop="property" content="worker_device_index"/>
<meta itemprop="property" content="worker_devices"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="batch_reduce"/>
<meta itemprop="property" content="broadcast"/>
<meta itemprop="property" content="call_for_each_tower"/>
<meta itemprop="property" content="colocate_vars_with"/>
<meta itemprop="property" content="configure"/>
<meta itemprop="property" content="distribute_dataset"/>
<meta itemprop="property" content="group"/>
<meta itemprop="property" content="map"/>
<meta itemprop="property" content="non_slot_devices"/>
<meta itemprop="property" content="read_var"/>
<meta itemprop="property" content="reduce"/>
<meta itemprop="property" content="scope"/>
<meta itemprop="property" content="unwrap"/>
<meta itemprop="property" content="update"/>
<meta itemprop="property" content="update_non_slot"/>
</div>

# tf.contrib.distribute.OneDeviceStrategy

## Class `OneDeviceStrategy`

Inherits From: [`DistributionStrategy`](../../../tf/contrib/distribute/DistributionStrategy.md)



Defined in [`tensorflow/contrib/distribute/python/one_device_strategy.py`](https://www.tensorflow.org/code/tensorflow/contrib/distribute/python/one_device_strategy.py).

A distribution strategy for running on a single device.

## Properties

<h3 id="is_single_tower"><code>is_single_tower</code></h3>

Returns whether there is a single tower or multiple.

#### Returns:

A boolean. If `True`, `call_for_each_tower(fn)` will only call `fn` once.
If `False`, `call_for_each_tower(fn)` may call `fn` multiple times.

<h3 id="num_towers"><code>num_towers</code></h3>

Returns number of towers, for purposes of averaging across towers.

<h3 id="parameter_devices"><code>parameter_devices</code></h3>

Returns the list of devices used for variable and `update` placement.

<h3 id="worker_device_index"><code>worker_device_index</code></h3>

An object mapping worker device to an id.

This might be passed as an argument to `call_for_each_tower()`, as in:

```
with distribution_strategy.scope():

  def fn(device_id):
    # device_id is an integer. `fn` is being executed on device:
    #    distribution_strategy.worker_devices[device_id].

  distribution_strategy.call_for_each_tower(
      fn, distribution_strategy.worker_device_index)
```

#### Returns:

An index object, or the integer 0 if there is only a single tower.

<h3 id="worker_devices"><code>worker_devices</code></h3>

Returns the list of devices used to run `call_for_each_tower()` calls.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    device,
    prefetch_on_device=None
)
```

Initialize self.  See help(type(self)) for accurate signature.

<h3 id="batch_reduce"><code>batch_reduce</code></h3>

``` python
batch_reduce(
    aggregation,
    value_destination_pairs
)
```

Combine multiple `reduce` calls into one for faster execution.

#### Args:

* <b>`aggregation`</b>: Indicates how a variable will be aggregated. Accepted values
    are <a href="../../../tf/VariableAggregation.md#SUM"><code>tf.VariableAggregation.SUM</code></a>, <a href="../../../tf/VariableAggregation.md#MEAN"><code>tf.VariableAggregation.MEAN</code></a>.
* <b>`value_destination_pairs`</b>: A sequence of (value, destinations)
    pairs. See `reduce()` for a description.


#### Returns:

A list of mirrored values, one per pair in `value_destination_pairs`.

<h3 id="broadcast"><code>broadcast</code></h3>

``` python
broadcast(
    tensor,
    destinations=None
)
```

Mirror a tensor on one device to all worker devices.

#### Args:

* <b>`tensor`</b>: A Tensor value to broadcast.
* <b>`destinations`</b>: An optional mirrored variable, device string, or
    list of device strings, specifying the destination devices
    to copy `tensor` to. Defaults to `self.worker_devices`.


#### Returns:

A value mirrored to `destinations` devices.

<h3 id="call_for_each_tower"><code>call_for_each_tower</code></h3>

``` python
call_for_each_tower(
    fn,
    *args,
    **kwargs
)
```

Run `fn` once per tower.

`fn` may call `tf.get_tower_context()` to access methods such as
`tower_id()` and `merge_call()`.

`merge_call()` is used to communicate between the towers and
re-enter the cross-tower context. All towers pause their execution
having encountered a `merge_call()` call. After that the
`merge_fn`-function is executed. Its results are then unwrapped and
given back to each tower call. After that execution resumes until
`fn` is complete or encounters another `merge_call()`.  Example:

```python
# Called once in "cross-tower" context.
def merge_fn(distribution, three_plus_tower_id):
  # sum the values across towers
  return sum(distribution.unwrap(three_plus_tower_id))

# Called once per tower in `distribution`, in a "tower" context.
def fn(three):
  tower_ctx = tf.get_tower_context()
  v = three + tower_ctx.tower_id
  # Computes the sum of the `v` values across all towers.
  s = tower_ctx.merge_call(merge_fn, v)
  return s + v

with distribution.scope():
  # in "cross-tower" context
  ...
  merged_results = distribution.call_for_each_tower(fn, 3)
  # merged_results has the values from every tower execution of `fn`.
  print(distribution.unwrap(merged_results))  # Prints a list
```

#### Args:

* <b>`fn`</b>: function to run (will be run once per tower).
* <b>`*args`</b>: positional arguments for `fn`
* <b>`**kwargs`</b>: keyword arguments for `fn`.
      `"run_concurrently"`: Boolean indicating whether executions of `fn`
         can be run concurrently (under eager execution only), defaults to
         `True`.


#### Returns:

Merged return value of `fn` across all towers.

<h3 id="colocate_vars_with"><code>colocate_vars_with</code></h3>

``` python
colocate_vars_with(colocate_with_variable)
```

Scope that controls which devices variables will be created on.

No operations should be added to the graph inside this scope, it
should only be used when creating variables (some implementations
work by changing variable creation, others work by using a
tf.colocate_with() scope).

This may only be used inside `self.scope()`.

Example usage:

```
with distribution_strategy.scope():
  var1 = tf.get_variable(...)
  with distribution_strategy.colocate_vars_with(v1):
    # var2 and var3 will be created on the same device(s) as var1
    var2 = tf.get_variable(...)
    var3 = tf.get_variable(...)

  def fn(v1, v2, v3):
    # operates on v1 from var1, v2 from var2, and v3 from var3

  # `fn` runs on every device `v1` is on, `v2` and `v3` will be there too.
  distribution_strategy.update(v1, fn, v2, v3)
```

#### Args:

* <b>`colocate_with_variable`</b>: A created in `self.scope()`. Variables created
    while in the returned context manager will be on the same set of
    devices as `colocate_with_variable`.


#### Returns:

A context manager.

<h3 id="configure"><code>configure</code></h3>

``` python
configure(session_config=None)
```

Find the best configuration given a tensorflow session config.

<h3 id="distribute_dataset"><code>distribute_dataset</code></h3>

``` python
distribute_dataset(dataset_fn)
```

Return a `dataset` split across all towers.

Suitable for providing input to for `call_for_each_tower()` by creating an
iterator:

```
def dataset_fn():
  return tf.data.Dataset.from_tensors([[1.]]).repeat()
with distribution_strategy.scope():
  distributed_dataset = distribution_strategy.distribute_dataset(dataset_fn)
  iterator = distributed_dataset.make_one_shot_iterator()
  tower_results = distribution_strategy.call_for_each_tower(
      tower_fn, iterator.get_next())
```

#### Args:

* <b>`dataset_fn`</b>: A function that returns a <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a>.


#### Returns:

A `PerDeviceDataset` that will produce data for each tower.

<h3 id="group"><code>group</code></h3>

``` python
group(
    value,
    name=None
)
```

Shortcut for `tf.group(distribution.unwrap(value))`.

<h3 id="map"><code>map</code></h3>

``` python
map(
    map_over,
    fn,
    *args,
    **kwargs
)
```



<h3 id="non_slot_devices"><code>non_slot_devices</code></h3>

``` python
non_slot_devices(var_list)
```

Device(s) for non-slot variables.

Create variables on these devices in a
`with colocate_vars_with(non_slot_devices(...)):` block.
Update those using `update_non_slot()`.

#### Args:

* <b>`var_list`</b>: The list of variables being optimized, needed with the
    default `DistributionStrategy`.

<h3 id="read_var"><code>read_var</code></h3>

``` python
read_var(tower_local_var)
```

Read the aggregate value of a tower-local variable.

<h3 id="reduce"><code>reduce</code></h3>

``` python
reduce(
    aggregation,
    value,
    destinations=None
)
```

Combine (via e.g. sum or mean) values across towers.

#### Args:

* <b>`aggregation`</b>: Indicates how a variable will be aggregated. Accepted values
    are <a href="../../../tf/VariableAggregation.md#SUM"><code>tf.VariableAggregation.SUM</code></a>, <a href="../../../tf/VariableAggregation.md#MEAN"><code>tf.VariableAggregation.MEAN</code></a>.
* <b>`value`</b>: A per-device value with one value per tower.
* <b>`destinations`</b>: An optional mirrored variable, a device string,
    list of device strings. The return value will be copied to all
    destination devices (or all the devices where the mirrored
    variable resides). If `None` or unspecified, the destinations
    will match the devices `value` resides on.


#### Returns:

A value mirrored to `destinations`.

<h3 id="scope"><code>scope</code></h3>

``` python
scope()
```

Returns a context manager selecting this DistributionStrategy as current.

Inside a `with distribution_strategy.scope():` code block, this thread
will use a variable creator set by `distribution_strategy`, and will
enter its "cross-tower context".

#### Returns:

A context manager.

<h3 id="unwrap"><code>unwrap</code></h3>

``` python
unwrap(value)
```

Returns the list of all per-device values contained in `value`.

#### Args:

* <b>`value`</b>: A value returned by `call_for_each_tower()` or a variable
    created in `scope()`.


#### Returns:

A list of values contained in `value`. If `value` represents a single
value, this returns `[value].`

<h3 id="update"><code>update</code></h3>

``` python
update(
    var,
    fn,
    *args,
    **kwargs
)
```

Run `fn` to update `var` using inputs mirrored to the same devices.

If `var` is mirrored across multiple devices, then this implements
logic like:

```
results = {}
for device, v in var:
  with tf.device(device):
    # *args and **kwargs will be unwrapped if they are mirrored.
    results[device] = fn(v, *args, **kwargs)
return merged(results)
```

Otherwise this returns `fn(var, *args, **kwargs)` colocated with `var`.'

Neither *args nor **kwargs may contain per-device values.
If they contain mirrored values, they will be unwrapped before
calling `fn`.

#### Args:

* <b>`var`</b>: Variable, possibly mirrored to multiple devices, to operate on.
* <b>`fn`</b>: Function to call. Should take the variable as the first argument.
* <b>`*args`</b>: Additional positional arguments to pass to `fn()`.
* <b>`**kwargs`</b>: Keyword arguments to pass to `fn()`.


#### Returns:

Merged return value of `fn` across all towers.

<h3 id="update_non_slot"><code>update_non_slot</code></h3>

``` python
update_non_slot(
    colocate_with,
    fn,
    *args,
    **kwargs
)
```

Runs `fn(*args, **kwargs)` on `colocate_with` devices.

#### Args:

* <b>`colocate_with`</b>: The return value of `non_slot_devices()`.
* <b>`fn`</b>: Function to execute.
* <b>`*args`</b>: Positional arguments to pass to `fn()`.
* <b>`**kwargs`</b>: Keyword arguments to pass to `fn()`.


#### Returns:

Return value of `fn`, possibly merged across devices.




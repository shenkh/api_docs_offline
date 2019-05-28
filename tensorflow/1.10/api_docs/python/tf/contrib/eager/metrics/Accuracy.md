<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.eager.metrics.Accuracy" />
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="variables"/>
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="add_variable"/>
<meta itemprop="property" content="aggregate"/>
<meta itemprop="property" content="build"/>
<meta itemprop="property" content="call"/>
<meta itemprop="property" content="init_variables"/>
<meta itemprop="property" content="result"/>
<meta itemprop="property" content="value"/>
</div>

# tf.contrib.eager.metrics.Accuracy

## Class `Accuracy`

Inherits From: [`Mean`](../../../../tf/contrib/eager/metrics/Mean.md)



Defined in [`tensorflow/contrib/eager/python/metrics_impl.py`](https://www.tensorflow.org/code/tensorflow/contrib/eager/python/metrics_impl.py).

Calculates how often `predictions` matches `labels`.
#### Attributes:

* <b>`name`</b>: name of the accuracy object
* <b>`dtype`</b>: data type of the tensor

## Properties

<h3 id="name"><code>name</code></h3>



<h3 id="variables"><code>variables</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    name=None,
    dtype=tf.double
)
```

Inits Accuracy class with name and dtype.

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    *args,
    **kwargs
)
```

Returns op to execute to update this metric for these inputs.

Returns None if eager execution is enabled.
Returns a graph-mode function if graph execution is enabled.

#### Args:

* <b>`*args`</b>: * <b>`**kwargs`</b>: A mini-batch of inputs to the Metric, passed on to `call()`.

<h3 id="add_variable"><code>add_variable</code></h3>

``` python
add_variable(
    name,
    shape=None,
    dtype=None,
    initializer=None
)
```

***Only for use by descendants of Metric***.

<h3 id="aggregate"><code>aggregate</code></h3>

``` python
aggregate(metrics)
```

Adds in the state from a list of metrics.

Default implementation sums all the metric variables.

#### Args:

* <b>`metrics`</b>: A list of metrics with the same type as `self`.


#### Raises:

* <b>`ValueError`</b>: If metrics contains invalid data.

<h3 id="build"><code>build</code></h3>

``` python
build(
    *args,
    **kwargs
)
```

Method to create variables.

Called by `__call__()` before `call()` for the first time.

#### Args:

* <b>`*args`</b>: * <b>`**kwargs`</b>: The arguments to the first invocation of `__call__()`.
   `build()` may use the shape and/or dtype of these arguments
   when deciding how to create variables.

<h3 id="call"><code>call</code></h3>

``` python
call(
    labels,
    predictions,
    weights=None
)
```

Accumulate accuracy statistics.

For example, if labels is [1, 2, 3, 4] and predictions is [0, 2, 3, 4]
then the accuracy is 3/4 or .75.  If the weights were specified as
[1, 1, 0, 0] then the accuracy would be 1/2 or .5.

`labels` and `predictions` should have the same shape and type.

#### Args:

* <b>`labels`</b>: Tensor with the true labels for each example.  One example
    per element of the Tensor.
* <b>`predictions`</b>: Tensor with the predicted label for each example.
* <b>`weights`</b>: Optional weighting of each example. Defaults to 1.


#### Returns:

The arguments, for easy chaining.

<h3 id="init_variables"><code>init_variables</code></h3>

``` python
init_variables()
```

Initializes this Metric's variables.

Should be called after variables are created in the first execution
of `__call__()`. If using graph execution, the return value should be
`run()` in a session before running the op returned by `__call__()`.
(See example above.)

#### Returns:

If using graph execution, this returns an op to perform the
initialization. Under eager execution, the variables are reset to their
initial values as a side effect and this function returns None.

<h3 id="result"><code>result</code></h3>

``` python
result()
```

Computes and returns a final value for the metric.

<h3 id="value"><code>value</code></h3>

``` python
value()
```

In graph mode returns the result Tensor while in eager the callable.




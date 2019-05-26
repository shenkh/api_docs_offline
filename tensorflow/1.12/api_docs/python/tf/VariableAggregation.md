<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.VariableAggregation" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="MEAN"/>
<meta itemprop="property" content="NONE"/>
<meta itemprop="property" content="ONLY_FIRST_TOWER"/>
<meta itemprop="property" content="SUM"/>
<meta itemprop="property" content="__members__"/>
</div>

# tf.VariableAggregation

## Class `VariableAggregation`





Defined in [`tensorflow/python/ops/variables.py`](/code/stable/tensorflow/python/ops/variables.py).

Indicates how a distributed variable will be aggregated.

<a href="../tf/contrib/distribute/DistributionStrategy.md"><code>tf.contrib.distribute.DistributionStrategy</code></a> distributes a model by making
multiple copies (called "towers") acting data-parallel on different elements
of the input batch. When performing some variable-update operation, say
`var.assign_add(x)`, in a model, we need to resolve how to combine the
different values for `x` computed in the different towers.

* `NONE`: This is the default, giving an error if you use a
  variable-update operation with multiple towers.
* `SUM`: Add the updates across towers.
* `MEAN`: Take the arithmetic mean ("average") of the updates across towers.
* `ONLY_FIRST_TOWER`: This is for when every tower is performing the same
  update, but we only want to perform the update once. Used, e.g., for the
  global step counter.

## Class Members

<h3 id="MEAN"><code>MEAN</code></h3>

<h3 id="NONE"><code>NONE</code></h3>

<h3 id="ONLY_FIRST_TOWER"><code>ONLY_FIRST_TOWER</code></h3>

<h3 id="SUM"><code>SUM</code></h3>

<h3 id="__members__"><code>__members__</code></h3>


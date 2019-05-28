<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.Reduction" />
<meta itemprop="property" content="all"/>
<meta itemprop="property" content="validate"/>
<meta itemprop="property" content="MEAN"/>
<meta itemprop="property" content="NONE"/>
<meta itemprop="property" content="SUM"/>
<meta itemprop="property" content="SUM_BY_NONZERO_WEIGHTS"/>
<meta itemprop="property" content="SUM_OVER_BATCH_SIZE"/>
<meta itemprop="property" content="SUM_OVER_NONZERO_WEIGHTS"/>
</div>

# tf.losses.Reduction

## Class `Reduction`





Defined in [`tensorflow/python/ops/losses/losses_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/losses/losses_impl.py).

Types of loss reduction.

Contains the following values:
`NONE`: Un-reduced weighted losses with the same shape as input.
`SUM`: Scalar sum of weighted losses.
`MEAN`: Scalar `SUM` divided by sum of weights.
`SUM_OVER_BATCH_SIZE`: Scalar `SUM` divided by number of elements in losses.
`SUM_OVER_NONZERO_WEIGHTS`: Scalar `SUM` divided by number of non-zero
   weights.
`SUM_BY_NONZERO_WEIGHTS`: Same as `SUM_OVER_NONZERO_WEIGHTS`.

## Methods

<h3 id="all"><code>all</code></h3>

``` python
@classmethod
all(cls)
```



<h3 id="validate"><code>validate</code></h3>

``` python
@classmethod
validate(
    cls,
    key
)
```





## Class Members

<h3 id="MEAN"><code>MEAN</code></h3>

<h3 id="NONE"><code>NONE</code></h3>

<h3 id="SUM"><code>SUM</code></h3>

<h3 id="SUM_BY_NONZERO_WEIGHTS"><code>SUM_BY_NONZERO_WEIGHTS</code></h3>

<h3 id="SUM_OVER_BATCH_SIZE"><code>SUM_OVER_BATCH_SIZE</code></h3>

<h3 id="SUM_OVER_NONZERO_WEIGHTS"><code>SUM_OVER_NONZERO_WEIGHTS</code></h3>


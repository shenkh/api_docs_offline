<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.MapVectorizationOptions" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="enabled"/>
<meta itemprop="property" content="use_choose_fastest"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__ne__"/>
</div>

# tf.data.experimental.MapVectorizationOptions

## Class `MapVectorizationOptions`

Represents options for the MapVectorization optimization.



### Aliases:

* Class `tf.compat.v1.data.experimental.MapVectorizationOptions`
* Class `tf.compat.v2.data.experimental.MapVectorizationOptions`
* Class `tf.data.experimental.MapVectorizationOptions`



Defined in [`python/data/experimental/ops/optimization_options.py`](/code/stable/tensorflow/python/data/experimental/ops/optimization_options.py).

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__()
```

Initialize self.  See help(type(self)) for accurate signature.




## Properties

<h3 id="enabled"><code>enabled</code></h3>

Whether to vectorize map transformations. If None, defaults to False.


<h3 id="use_choose_fastest"><code>use_choose_fastest</code></h3>

Whether to use ChooseFastestBranchDataset with this transformation. If True, the pipeline picks between the vectorized and original segment at runtime based on their iterations speed. If None, defaults to False.




## Methods

<h3 id="__eq__"><code>__eq__</code></h3>

``` python
__eq__(other)
```

Return self==value.


<h3 id="__ne__"><code>__ne__</code></h3>

``` python
__ne__(other)
```

Return self!=value.





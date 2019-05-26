<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.model_pruning.Pruning" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="add_pruning_summaries"/>
<meta itemprop="property" content="conditional_mask_update_op"/>
<meta itemprop="property" content="mask_update_op"/>
<meta itemprop="property" content="print_hparams"/>
</div>

# tf.contrib.model_pruning.Pruning

## Class `Pruning`





Defined in [`tensorflow/contrib/model_pruning/python/pruning.py`](/code/stable/tensorflow/contrib/model_pruning/python/pruning.py).



<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    spec=None,
    global_step=None,
    sparsity=None
)
```

Set up the specification for model pruning.

If a spec is provided, the sparsity is set up based on the sparsity_function
in the spec. The effect of sparsity_function is overridden if the sparsity
variable is passed to the constructor. This enables setting up arbitrary
sparsity profiles externally and passing it to this pruning functions.

#### Args:

* <b>`spec`</b>: Pruning spec as defined in pruning.proto
* <b>`global_step`</b>: A tensorflow variable that is used while setting up the
    sparsity function
* <b>`sparsity`</b>: A tensorflow scalar variable storing the sparsity



## Methods

<h3 id="add_pruning_summaries"><code>add_pruning_summaries</code></h3>

``` python
add_pruning_summaries()
```

Adds summaries of weight sparsities and thresholds.

<h3 id="conditional_mask_update_op"><code>conditional_mask_update_op</code></h3>

``` python
conditional_mask_update_op()
```



<h3 id="mask_update_op"><code>mask_update_op</code></h3>

``` python
mask_update_op()
```



<h3 id="print_hparams"><code>print_hparams</code></h3>

``` python
print_hparams()
```






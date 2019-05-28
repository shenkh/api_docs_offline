<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.fisher_factors.set_global_constants" />
</div>

# tf.contrib.kfac.fisher_factors.set_global_constants

``` python
tf.contrib.kfac.fisher_factors.set_global_constants(
    init_covariances_at_zero=None,
    zero_debias=None,
    init_inverses_at_zero=None,
    eigenvalue_decomposition_threshold=None,
    eigenvalue_clipping_threshold=None,
    max_num_outer_products_per_cov_row=None,
    sub_sample_outer_products=None,
    inputs_to_extract_patches_factor=None,
    sub_sample_inputs=None,
    tower_strategy=None
)
```



Defined in [`tensorflow/contrib/kfac/python/ops/fisher_factors.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/fisher_factors.py).

Sets various global constants used by the classes in this module.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.wrappers.scikit_learn.KerasClassifier" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="check_params"/>
<meta itemprop="property" content="filter_sk_params"/>
<meta itemprop="property" content="fit"/>
<meta itemprop="property" content="get_params"/>
<meta itemprop="property" content="predict"/>
<meta itemprop="property" content="predict_proba"/>
<meta itemprop="property" content="score"/>
<meta itemprop="property" content="set_params"/>
</div>

# tf.keras.wrappers.scikit_learn.KerasClassifier

## Class `KerasClassifier`

Implementation of the scikit-learn classifier API for Keras.



### Aliases:

* Class `tf.compat.v1.keras.wrappers.scikit_learn.KerasClassifier`
* Class `tf.compat.v2.keras.wrappers.scikit_learn.KerasClassifier`
* Class `tf.keras.wrappers.scikit_learn.KerasClassifier`



Defined in [`python/keras/wrappers/scikit_learn.py`](/code/stable/tensorflow/python/keras/wrappers/scikit_learn.py).

<!-- Placeholder for "Used in" -->
  

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    build_fn=None,
    **sk_params
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="check_params"><code>check_params</code></h3>

``` python
check_params(params)
```

Checks for user typos in `params`.


#### Arguments:


* <b>`params`</b>: dictionary; the parameters to be checked


#### Raises:


* <b>`ValueError`</b>: if any member of `params` is not a valid argument.

<h3 id="filter_sk_params"><code>filter_sk_params</code></h3>

``` python
filter_sk_params(
    fn,
    override=None
)
```

Filters `sk_params` and returns those in `fn`'s arguments.


#### Arguments:


* <b>`fn`</b>: arbitrary function
* <b>`override`</b>: dictionary, values to override `sk_params`


#### Returns:


* <b>`res`</b>: dictionary containing variables
    in both `sk_params` and `fn`'s arguments.

<h3 id="fit"><code>fit</code></h3>

``` python
fit(
    x,
    y,
    **kwargs
)
```

Constructs a new model with `build_fn` & fit the model to `(x, y)`.


#### Arguments:


* <b>`x`</b>: array-like, shape `(n_samples, n_features)`
    Training samples where `n_samples` is the number of samples
    and `n_features` is the number of features.
* <b>`y`</b>: array-like, shape `(n_samples,)` or `(n_samples, n_outputs)`
    True labels for `x`.
* <b>`**kwargs`</b>: dictionary arguments
    Legal arguments are the arguments of `Sequential.fit`


#### Returns:


* <b>`history`</b>: object
    details about the training history at each epoch.


#### Raises:


* <b>`ValueError`</b>: In case of invalid shape for `y` argument.

<h3 id="get_params"><code>get_params</code></h3>

``` python
get_params(**params)
```

Gets parameters for this estimator.


#### Arguments:


* <b>`**params`</b>: ignored (exists for API compatibility).


#### Returns:

Dictionary of parameter names mapped to their values.


<h3 id="predict"><code>predict</code></h3>

``` python
predict(
    x,
    **kwargs
)
```

Returns the class predictions for the given test data.


#### Arguments:


* <b>`x`</b>: array-like, shape `(n_samples, n_features)`
    Test samples where `n_samples` is the number of samples
    and `n_features` is the number of features.
* <b>`**kwargs`</b>: dictionary arguments
    Legal arguments are the arguments
    of `Sequential.predict_classes`.


#### Returns:


* <b>`preds`</b>: array-like, shape `(n_samples,)`
    Class predictions.

<h3 id="predict_proba"><code>predict_proba</code></h3>

``` python
predict_proba(
    x,
    **kwargs
)
```

Returns class probability estimates for the given test data.


#### Arguments:


* <b>`x`</b>: array-like, shape `(n_samples, n_features)`
    Test samples where `n_samples` is the number of samples
    and `n_features` is the number of features.
* <b>`**kwargs`</b>: dictionary arguments
    Legal arguments are the arguments
    of `Sequential.predict_classes`.


#### Returns:


* <b>`proba`</b>: array-like, shape `(n_samples, n_outputs)`
    Class probability estimates.
    In the case of binary classification,
    to match the scikit-learn API,
    will return an array of shape `(n_samples, 2)`
    (instead of `(n_sample, 1)` as in Keras).

<h3 id="score"><code>score</code></h3>

``` python
score(
    x,
    y,
    **kwargs
)
```

Returns the mean accuracy on the given test data and labels.


#### Arguments:


* <b>`x`</b>: array-like, shape `(n_samples, n_features)`
    Test samples where `n_samples` is the number of samples
    and `n_features` is the number of features.
* <b>`y`</b>: array-like, shape `(n_samples,)` or `(n_samples, n_outputs)`
    True labels for `x`.
* <b>`**kwargs`</b>: dictionary arguments
    Legal arguments are the arguments of `Sequential.evaluate`.


#### Returns:


* <b>`score`</b>: float
    Mean accuracy of predictions on `x` wrt. `y`.


#### Raises:


* <b>`ValueError`</b>: If the underlying model isn't configured to
    compute accuracy. You should pass `metrics=["accuracy"]` to
    the `.compile()` method of the model.

<h3 id="set_params"><code>set_params</code></h3>

``` python
set_params(**params)
```

Sets the parameters of this estimator.


#### Arguments:


* <b>`**params`</b>: Dictionary of parameter names mapped to their values.


#### Returns:

self





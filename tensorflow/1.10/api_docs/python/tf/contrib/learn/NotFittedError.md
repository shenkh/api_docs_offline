<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.learn.NotFittedError" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.contrib.learn.NotFittedError

## Class `NotFittedError`





Defined in [`tensorflow/contrib/learn/python/learn/estimators/_sklearn.py`](https://www.tensorflow.org/code/tensorflow/contrib/learn/python/learn/estimators/_sklearn.py).

Exception class to raise if estimator is used before fitting.

USE OF THIS EXCEPTION IS DEPRECATED.

This class inherits from both ValueError and AttributeError to help with
exception handling and backward compatibility.

Examples:
>>> from sklearn.svm import LinearSVC
>>> from sklearn.exceptions import NotFittedError
>>> try:
...     LinearSVC().predict([[1, 2], [2, 3], [3, 4]])
... except NotFittedError as e:
...     print(repr(e))
...                        # doctest: +NORMALIZE_WHITESPACE +ELLIPSIS
NotFittedError('This LinearSVC instance is not fitted yet',)

Copied from
https://github.com/scikit-learn/scikit-learn/master/sklearn/exceptions.py

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    *args,
    **kwargs
)
```



<h3 id="__new__"><code>__new__</code></h3>

``` python
__new__(
    type,
    *args,
    **kwargs
)
```






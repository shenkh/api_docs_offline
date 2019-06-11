<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.datasets.cifar100.load_data" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.datasets.cifar100.load_data

Loads CIFAR100 dataset.

### Aliases:

* `tf.compat.v1.keras.datasets.cifar100.load_data`
* `tf.compat.v2.keras.datasets.cifar100.load_data`
* `tf.keras.datasets.cifar100.load_data`

``` python
tf.keras.datasets.cifar100.load_data(label_mode='fine')
```



Defined in [`python/keras/datasets/cifar100.py`](/code/stable/tensorflow/python/keras/datasets/cifar100.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`label_mode`</b>: one of "fine", "coarse".


#### Returns:

Tuple of Numpy arrays: `(x_train, y_train), (x_test, y_test)`.



#### Raises:


* <b>`ValueError`</b>: in case of invalid `label_mode`.
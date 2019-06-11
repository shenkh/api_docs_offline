<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image.Iterator" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__getitem__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__iter__"/>
<meta itemprop="property" content="__len__"/>
<meta itemprop="property" content="next"/>
<meta itemprop="property" content="on_epoch_end"/>
<meta itemprop="property" content="reset"/>
<meta itemprop="property" content="white_list_formats"/>
</div>

# tf.keras.preprocessing.image.Iterator

## Class `Iterator`

Base class for image data iterators.

Inherits From: [`Sequence`](../../../../tf/keras/utils/Sequence.md)

### Aliases:

* Class `tf.compat.v1.keras.preprocessing.image.Iterator`
* Class `tf.compat.v2.keras.preprocessing.image.Iterator`
* Class `tf.keras.preprocessing.image.Iterator`



Defined in [`python/keras/preprocessing/image.py`](/code/stable/tensorflow/python/keras/preprocessing/image.py).

<!-- Placeholder for "Used in" -->

Every `Iterator` must implement the `_get_batches_of_transformed_samples`
method.

# Arguments
    n: Integer, total number of samples in the dataset to loop over.
    batch_size: Integer, size of a batch.
    shuffle: Boolean, whether to shuffle the data between epochs.
    seed: Random seeding for data shuffling.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    n,
    batch_size,
    shuffle,
    seed
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="__getitem__"><code>__getitem__</code></h3>

``` python
__getitem__(idx)
```

Gets batch at position `index`.


#### Arguments:


* <b>`index`</b>: position of the batch in the Sequence.


#### Returns:

A batch


<h3 id="__iter__"><code>__iter__</code></h3>

``` python
__iter__()
```

Create a generator that iterate over the Sequence.


<h3 id="__len__"><code>__len__</code></h3>

``` python
__len__()
```

Number of batch in the Sequence.


#### Returns:

The number of batches in the Sequence.


<h3 id="next"><code>next</code></h3>

``` python
next()
```

For python 2.x.

# Returns
    The next batch.

<h3 id="on_epoch_end"><code>on_epoch_end</code></h3>

``` python
on_epoch_end()
```

Method called at the end of every epoch.
    

<h3 id="reset"><code>reset</code></h3>

``` python
reset()
```






## Class Members

* `white_list_formats` <a id="white_list_formats"></a>

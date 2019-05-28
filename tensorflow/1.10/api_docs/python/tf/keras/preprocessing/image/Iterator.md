<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image.Iterator" />
<meta itemprop="property" content="__getitem__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__iter__"/>
<meta itemprop="property" content="__len__"/>
<meta itemprop="property" content="__next__"/>
<meta itemprop="property" content="on_epoch_end"/>
<meta itemprop="property" content="reset"/>
</div>

# tf.keras.preprocessing.image.Iterator

## Class `Iterator`

Inherits From: [`Sequence`](../../../../tf/keras/utils/Sequence.md)



Defined in [`tensorflow/python/keras/preprocessing/image.py`](https://www.tensorflow.org/code/tensorflow/python/keras/preprocessing/image.py).

Base class for image data iterators.

Every `Iterator` must implement the `_get_batches_of_transformed_samples`
method.

#### Arguments:

* <b>`n`</b>: Integer, total number of samples in the dataset to loop over.
* <b>`batch_size`</b>: Integer, size of a batch.
* <b>`shuffle`</b>: Boolean, whether to shuffle the data between epochs.
* <b>`seed`</b>: Random seeding for data shuffling.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    n,
    batch_size,
    shuffle,
    seed
)
```

Initialize self.  See help(type(self)) for accurate signature.

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

Creates an infinite generator that iterate over the Sequence.

#### Yields:

Sequence items.

<h3 id="__len__"><code>__len__</code></h3>

``` python
__len__()
```

Number of batch in the Sequence.

#### Returns:

The number of batches in the Sequence.

<h3 id="__next__"><code>__next__</code></h3>

``` python
__next__(
    *args,
    **kwargs
)
```



<h3 id="on_epoch_end"><code>on_epoch_end</code></h3>

``` python
on_epoch_end()
```

Method called at the end of every epoch.
    

<h3 id="reset"><code>reset</code></h3>

``` python
reset()
```






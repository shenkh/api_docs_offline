<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.sequence.TimeseriesGenerator" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__getitem__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__iter__"/>
<meta itemprop="property" content="__len__"/>
<meta itemprop="property" content="get_config"/>
<meta itemprop="property" content="on_epoch_end"/>
<meta itemprop="property" content="to_json"/>
</div>

# tf.keras.preprocessing.sequence.TimeseriesGenerator

## Class `TimeseriesGenerator`

Utility class for generating batches of temporal data.

Inherits From: [`Sequence`](../../../../tf/keras/utils/Sequence.md)

### Aliases:

* Class `tf.compat.v1.keras.preprocessing.sequence.TimeseriesGenerator`
* Class `tf.compat.v2.keras.preprocessing.sequence.TimeseriesGenerator`
* Class `tf.keras.preprocessing.sequence.TimeseriesGenerator`



Defined in [`python/keras/preprocessing/sequence.py`](/code/stable/tensorflow/python/keras/preprocessing/sequence.py).

<!-- Placeholder for "Used in" -->
This class takes in a sequence of data-points gathered at
equal intervals, along with time series parameters such as
stride, length of history, etc., to produce batches for
training/validation.
# Arguments
    data: Indexable generator (such as list or Numpy array)
        containing consecutive data points (timesteps).
        The data should be at 2D, and axis 0 is expected
        to be the time dimension.
    targets: Targets corresponding to timesteps in `data`.
        It should have same length as `data`.
    length: Length of the output sequences (in number of timesteps).
    sampling_rate: Period between successive individual timesteps
        within sequences. For rate `r`, timesteps
        `data[i]`, `data[i-r]`, ... `data[i - length]`
        are used for create a sample sequence.
    stride: Period between successive output sequences.
        For stride `s`, consecutive output samples would
        be centered around `data[i]`, `data[i+s]`, `data[i+2*s]`, etc.
    start_index: Data points earlier than `start_index` will not be used
        in the output sequences. This is useful to reserve part of the
        data for test or validation.
    end_index: Data points later than `end_index` will not be used
        in the output sequences. This is useful to reserve part of the
        data for test or validation.
    shuffle: Whether to shuffle output samples,
        or instead draw them in chronological order.
    reverse: Boolean: if `true`, timesteps in each output sample will be
        in reverse chronological order.
    batch_size: Number of timeseries samples in each batch
        (except maybe the last one).
# Returns
    A [Sequence](/utils/#sequence) instance.
# Examples
```python
from keras.preprocessing.sequence import TimeseriesGenerator
import numpy as np
data = np.array([[i] for i in range(50)])
targets = np.array([[i] for i in range(50)])
data_gen = TimeseriesGenerator(data, targets,
                               length=10, sampling_rate=2,
                               batch_size=2)
assert len(data_gen) == 20
batch_0 = data_gen[0]
x, y = batch_0
assert np.array_equal(x,
                      np.array([[[0], [2], [4], [6], [8]],
                                [[1], [3], [5], [7], [9]]]))
assert np.array_equal(y,
                      np.array([[10], [11]]))
```

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    data,
    targets,
    length,
    sampling_rate=1,
    stride=1,
    start_index=0,
    end_index=None,
    shuffle=False,
    reverse=False,
    batch_size=128
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="__getitem__"><code>__getitem__</code></h3>

``` python
__getitem__(index)
```




<h3 id="__iter__"><code>__iter__</code></h3>

``` python
__iter__()
```

Create a generator that iterate over the Sequence.


<h3 id="__len__"><code>__len__</code></h3>

``` python
__len__()
```




<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```

Returns the TimeseriesGenerator configuration as Python dictionary.

# Returns
    A Python dictionary with the TimeseriesGenerator configuration.

<h3 id="on_epoch_end"><code>on_epoch_end</code></h3>

``` python
on_epoch_end()
```

Method called at the end of every epoch.
    

<h3 id="to_json"><code>to_json</code></h3>

``` python
to_json(**kwargs)
```

Returns a JSON string containing the timeseries generator
configuration. To load a generator from a JSON string, use
`keras.preprocessing.sequence.timeseries_generator_from_json(json_string)`.

# Arguments
    **kwargs: Additional keyword arguments
        to be passed to `json.dumps()`.

# Returns
    A JSON string containing the tokenizer configuration.




<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.text.hashing_trick" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.preprocessing.text.hashing_trick

Converts a text to a sequence of indexes in a fixed-size hashing space.

### Aliases:

* `tf.compat.v1.keras.preprocessing.text.hashing_trick`
* `tf.compat.v2.keras.preprocessing.text.hashing_trick`
* `tf.keras.preprocessing.text.hashing_trick`

``` python
tf.keras.preprocessing.text.hashing_trick(
    text,
    n,
    hash_function=None,
    filters='!"#$%&()*+,-./:;<=>?@[\\]^_`{|}~\t\n',
    lower=True,
    split=' '
)
```

<!-- Placeholder for "Used in" -->

# Arguments
    text: Input text (string).
    n: Dimension of the hashing space.
    hash_function: defaults to python `hash` function, can be 'md5' or
        any function that takes in input a string and returns a int.
        Note that 'hash' is not a stable hashing function, so
        it is not consistent across different runs, while 'md5'
        is a stable hashing function.
    filters: list (or concatenation) of characters to filter out, such as
        punctuation. Default: ``!"#$%&()*+,-./:;<=>?@[\]^_`{|}~\t\n``,
        includes basic punctuation, tabs, and newlines.
    lower: boolean. Whether to set the text to lowercase.
    split: str. Separator for word splitting.

# Returns
    A list of integer word indices (unicity non-guaranteed).

`0` is a reserved index that won't be assigned to any word.

Two or more words may be assigned to the same index, due to possible
collisions by the hashing function.
The [probability](
    https://en.wikipedia.org/wiki/Birthday_problem#Probability_table)
of a collision is in relation to the dimension of the hashing space and
the number of distinct objects.
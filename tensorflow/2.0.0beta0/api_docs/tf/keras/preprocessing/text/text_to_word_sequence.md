<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.text.text_to_word_sequence" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.preprocessing.text.text_to_word_sequence

Converts a text to a sequence of words (or tokens).

### Aliases:

* `tf.compat.v1.keras.preprocessing.text.text_to_word_sequence`
* `tf.compat.v2.keras.preprocessing.text.text_to_word_sequence`
* `tf.keras.preprocessing.text.text_to_word_sequence`

``` python
tf.keras.preprocessing.text.text_to_word_sequence(
    text,
    filters='!"#$%&()*+,-./:;<=>?@[\\]^_`{|}~\t\n',
    lower=True,
    split=' '
)
```

<!-- Placeholder for "Used in" -->

# Arguments
    text: Input text (string).
    filters: list (or concatenation) of characters to filter out, such as
        punctuation. Default: ``!"#$%&()*+,-./:;<=>?@[\]^_`{|}~\t\n``,
        includes basic punctuation, tabs, and newlines.
    lower: boolean. Whether to convert the input to lowercase.
    split: str. Separator for word splitting.

# Returns
    A list of words (or tokens).
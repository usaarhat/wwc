# Session 3: Annotating data

In this session, we introduce part of speech tagging, use it to do lemmatisation, and develop a function that can concordance a tagged corpus.

## POS tagging

Some NLTK corpora have POS tags already in them:

```python
from nltk.corpus import brown
print(brown.words())
print(brown.tagged_words())
```

Let's extract adverbs from the Brown Corpus:

```python
adverbs = []
for word, tag in brown.tagged_words():
    # get any word whose tag is adverb
    if tag == 'RB':
        adverbs.append(word)
adverbs[:50]
```

You'll notice the method above as a common pattern in Python code. Declare an empty `list` or `dict`, iterate over a dataset, and add matches in there. This can turn into a lot of code though, so sometimes people use generator expressions:

```python
adverbs = [word for word, tag in brown.tagged_words() if tag == 'RB'][:50]
adverbs
```

What do you think of these two approaches?

## Adding POS tags

We can turn out plaintext into a POS tagged corpus just like the Brown Corpus (except lower accuracy!)

```python
with open('forum.txt', 'r', encoding = 'utf-8') as fo:
    plain = fo.read()
section = plain[5000:10000]
toks = nltk.word_tokenize(section)
tagged = nltk.pos_tag(text)
tagged[:20]
```

How easy was that?!

## Searching tagged corpora

Let's play around with our tagged corpus a little.

```python
for word, tag in tagged:
    if word.startswith('a') and tag.startswith('V'):
        print(word)
```

This could get quite a bit more powerful if we also use indexing:

```python
for index, (word, tag) in enumerate(tagged):
    if tag == 'MD':
        print(tagged[index + 1])
```

Try using some loops and conditions to find something cool! Suggestions:

1. Get long adjectives
2. Get a list of nouns that are only preceded by indefinite articles
3. Get the most common subjects in clauses with a modal finite
4. Try to find passive VPs
5. Get tokens that may be either nouns or verbs

## Lemmatisation

Last week, we did some stemming, and found that it's not very accurate. Why is this? Well, the basic problem is that you need to know a word's class in order to get its base form. Sure, it might make some sense to stem *liking* to *like*. But *loving* can also be nominal, as in *She had a liking for chocolate milk*. There, the stemming to *like* might not be so appropriate.

With POS tags, however, we can do lemmatisation, which is more accurate. The idea is to check dictionaries for words, and only use the heuristic approaches when the word isn't found.

```python
from nltk.stem.wordnet import WordNetLemmatizer
lmtzr=WordNetLemmatizer()
for word, tag in tagged[:50]:
    print(lmtzr.lemmatize(word, tag))
```

Problem? Yep. The lemmatiser doesn't take POS tags. Instead, it wants either `'n'`, `'v'`, `'a'`, or `'r'`. So, we need to write a translator.

```python
transtag = {'N': 'n',
            'V': 'v',
            'J': 'a',
            'R': 'r'}

for word, tag in tagged[:50]:
    if tag[0] in transtag.keys():
        newtag = transtag[tag[0]]
        print(lmtzr.lemmatize(word, newtag))
    else:
        print(word)
```

This works well, but it's a big ugly. Let's improve it a bit by using a function:

```python
def lemma(word, tag):
    """return lemma"""
    from nltk.stem.wordnet import WordNetLemmatizer
    lmtzr=WordNetLemmatizer()

    transtag = {'N': 'n',
                'V': 'v',
                'J': 'a',
                'R': 'r'}
    
    if tag[0] in transtag.keys():
        newtag = transtag[tag[0]]
        return lmtzr.lemmatize(word, newtag)
    else:
        return word
```

Now we can do something much nicer:

```python
for word, tag in tagged[:50]:
    print(lemma(word, tag))
```

Can you add the lemmatiser functionality to your old code?


```python
for index, (word, tag) in enumerate(tagged):
    if tag.startswith('J'):
        print(lemma(tagged[index + 1]))
```
## Return to concordancing

The final thing to cover in this session is concordancing. We already saw how NLTK's concordancer works:

```python
from nltk.book import *
text5.concordance('seriously')
```

... but we're also aware of its limitations. Concordancing can be very powerful, especially for thematic categorisation and the like. So, let's write up a concordancer for our plain text corpus

```python
def conc(query, text):
    """regex concordancer"""
    import re
    compiled = re.compile(r'(.*)(%s)(.*)' % query)
    lines = re.findall(compiled, text)
    for start, middle, end in lines:
        concline = [start[-30:], middle, end[:30]]
        print("\t".join(concline).expandtabs(35))
```

Let's try it out:

```python
conc('austral[a-z]+', plain)
```

Can you learn anything from our corpus by concordancing some important tokens?

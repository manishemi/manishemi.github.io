---
published: true
---

Distributed representation of words in vector space help learning algorithms to get better performance in NLP(Natural Language processing) task with grouping similar words. We can easily find similarities or dissimilarities using distance measures(such as [Euclidean distance](https://en.wikipedia.org/wiki/Euclidean_distance)) with word vectors.

But how we can represent words in vector space?

For representing words in vectors we have two options:

1 - One-hot

2 - Word Embedding(note it's not only for words)


## _One-hot_

|![_config.yml]({{ site.baseurl }}/images/Word2vec/one_hot.png)|
|:--:| 
| Figure 1: One-hot|

As you can see in figure 1 every word in this sentence is represented as a vector with size 8(our vocabulary size) which only the index of the corresponding word is 1 and the other words are 0. But this approach makes words independent of each other and obviously, this would be a bad idea to find similarities or differences.
For instance, if we dot product _**ate**_ vector and _**played**_ vector together we would get 0 and this means they don't have many similarities, but in fact, at least they have a similarity, they are both simple past.

## _Word Embedding_

|![_config.yml]({{ site.baseurl }}/images/Word2vec/embedding.png)|
|:--:| 
| Figure 2: Word Embedding|

Word Embedding is more complex than one-hot. In this approach, the word would be present as a vector with Embedding dimension _**N**_ (in figure 2 it's 4) that feeds with random numbers at the beginning. The numbers that constructed embedding vector are updating every step as same as the model's weights(word embedding vectors are trainable). For a better understanding of the embedding concept, imagine we have a word-like _**computer**_ that feeds with an embedding vector with dimension 100 then every number in this embedded vector describes one feature of computer like noun, singular, etc.


## _Skip-gram(SG)_

|![_config.yml]({{ site.baseurl }}/images/Word2vec/skip-gram1.png)|
|:--:| 
| Figure 3: Skip-gram model architecture|

The training objective of the Skip-model is to find word representations that are useful for 
predicting surrounding words. In another word, if we have a sentence that has _**T**_ words(**w1**, **w2**, **w3**, ...**wT**) that the model objective is to maximize average log probability.

|![_config.yml]({{ site.baseurl }}/images/Word2vec/log_prob.png)|

Where the _**c**_ is the size of training context, larger _**c**_ leads to higher accuracy but larger _**c**_ has a cost and that cost is the training time. The _**w_t**_ is the target word and _**w_t+j**_ is the context word

### An example of target and context word

|![_config.yml]({{ site.baseurl }}/images/Word2vec/window.gif)|
|:--:| 
|Figure 4: target and context word|


We can compute **P(w_t+j \| w_t)** (probability of context word given target word) using softmax fucntion.

|![_config.yml]({{ site.baseurl }}/images/Word2vec/softmax2.png)|

where _**vw**_ is input(target word) and _**v′w**_ is output(context word) vector representation of _**W**_, and _**W**_ is vocabulary size. But this formulation is impractical because the cost of computation is too much, imagine you have a dataset with 2 million words then the computation of the denominator would be too slow. So what is the alternative way?

### Negative Sampling

Negative sampling is an approach that can leads to less computation cost than the previous approach. In this approach for every training step, instead of looping over the entire vocabulary, we can just sample negative samples. The negative samples select randomly from vocabulary(they don't contain context words).

Let's denote by **P(D=1 \| w, c)** the probability that _**(w,c)**_ came from corpus data and 
**P(D=0 \| w,c)** or **1-P(D=1 \| w,c)** will be the probability that _**(w, c)**_ didn't come from corpus data.

|![_config.yml]({{ site.baseurl }}/images/Word2vec/p_negative.png)|
|:--:| 
|Figure 5: the probability that _**(w,c)**_ came from corpus|

Total loss would be:

|![_config.yml]({{ site.baseurl }}/images/Word2vec/total_loss.png)|
|:--:|
|Figure 6: Total loss|

### Difference between Skip-gram and negative sampling

|![_config.yml]({{ site.baseurl }}/images/Word2vec/skipgram-with-negative-sampling.png)|

In practice, we need labels for training our skip-gram model, which generates with skip-gram pair and negative sample pairs. For instance, if you have a sentence like “Shalt not make a machine” then the label with the target word “make” and with the number of negative samples 2 would be [1, 0, 0]

# Implementation

For coding concepts, you can visit the [Tensorflow Word2Vec](https://www.tensorflow.org/tutorials/text/word2vec), which implemented this algorithm on the text file of Shakespeare's writing. In addition, I implemented this algorithm on a Persian dataset as well. You can visit it from [here](https://github.com/manishemirani/Word2Vec_Persian).

# References

[Distributed Representations of Words and Phrases and their Compositionality Article](https://arxiv.org/abs/1310.4546)

[cs224n Stanford University NLP course](https://web.stanford.edu/class/archive/cs/cs224n/cs224n.1194/index.html)

[Tensorflow](https://www.tensorflow.org/tutorials/text/word2vec)

---
published: true
---
Machine Translation(**MT**) is a task that can translate a sentence **X** from one language(the source language) to a sentence **Y** from another language(the target language).

|![_config.yml]({{ site.baseurl }}/images/Machine Translation/MT_ex.png)|
|:--:| 
| Figure 1 : English to Germany|

In the past translation system were based on two parts:

1 - Translation model -> Defines what sentence/phrase in the source language is most likely to the target language sentence/phrase.

2 - Language model -> Defines the probability of each sentence/phrase could occur

But these models are not good enough to solve translation tasks, because they are based on phrases and this leads to our model can't capture the difference between languages.
We can solve this problem by using **Seq2Seq** architecture especially with using the [**LSTMs**](https://manishemirani.github.io/Long-Short-Term-Memory/) in this 
architecture.

# Seq2Seq

Sequence-to-Sequence(Seq2seq) is a model that made up with two recurrnet neural network.

1 - Encoder -> This layer takes a sentence from the source language and encodes it into a 'context vector'

2 - Decoder -> This layer takes a context vector(which is come from encoder output) as an initializer hidden state and starts predicting the target language words with knowing the information from source language

|![_config.yml]({{ site.baseurl }}/images/Machine Translation/seq2seq.gif)|
|:--:| 
| Figure 2 : Seq2Seq model|

This architecture has a problem. The problem is that all pieces of information about the source sentence are store in one vector(context vector). In another word for each step in RNNs the previous hidden state add to current hidden state with some forgotten and that means to in context vector we kinda have a summarization of previous hidden states. This problem calls the bottleneck problem.


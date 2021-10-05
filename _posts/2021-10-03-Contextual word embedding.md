---
published: true
---
One of the problems in the NLP is that the ordinary pre-trained word embeddings haven't contained the information about the context of each word in a specific sentence.

For instance, if we have a sentence like "Your mouse likes cheese" and "Buy a new mouse for your computer" if we use ordinary embedding for the word "mouse" we will get the same word embedding vector for both. In contextual word embedding, the goal is to have a different word embedding vector for each word in a specific situation.

|![_config.yml]({{ site.baseurl }}/images/BERT/problem_sentence.png)|
|:--:| 
| Figure 1: Same word embedding|

|![_config.yml]({{ site.baseurl }}/images/BERT/solution.png)|
|:--:| 
| Figure 2: Contextual word embedding|

these are three famous models that enable us to have contextual word embeddings:

1 - **BERT**(Bidirectional Encoder Representations from [Transformers](https://manishemirani.github.io/Attention-Is-All-You-Need/))

2 - **GPT**(it also comes with suffix 1, 2, 3)

3 - **ELMO**


# ELMO(Embedding from Language Models)

|![_config.yml]({{ site.baseurl }}/images/BERT/ELMO1.png)|
|:--:| 
| Figure 3: ELMO|

ELMO is a language model that is trained on a massive dataset to be able to predict the next word in a sequence of words. The ELMO is composed of two language models, Forward Language Model and Backward Language Model. These Language Models are similar to the [bi-directional LSTMs](https://manishemirani.github.io/Neural-Machine-translation/) that each [LSTM](https://manishemirani.github.io/Long-Short-Term-Memory/) trains separately in one direction(left or right).

|![_config.yml]({{ site.baseurl }}/images/BERT/ELMO2.png)|
|:--:| 
| Figure 4: ELMO architecture|

# GPT

GPT is also a language model that uses the decoder of the transformers instead of the LSTMs in ELMO. All the **GPT** models are composed of the decoder of the transformers. For example, the **GPT-2 SMALL** contains twelve decoder layers. This model(all GPTs) uses **masked self-attention** that helps the model to predict the next word just by using the previous words.

|![_config.yml]({{ site.baseurl }}/images/BERT/GPT-2.png)|
|:--:| 
| Figure 5: GPT-2|





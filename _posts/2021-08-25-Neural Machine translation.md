---
published: true
---
**Machine Translation**(MT) is a task that can translate a sentence **X** from one language(the source language) to a sentence **Y** from another language(the target language).

|![_config.yml]({{ site.baseurl }}/images/Machine Translation/MT_ex.png)|
|:--:| 
| Figure 1 : English to Germany|

In the past translation system were based on two parts:

1 - **Translation model** -> Defines what sentence/phrase in the source language is most likely to the target language sentence/phrase.

2 - **Language model** -> Defines the probability of each sentence/phrase could occur

But these models are not good enough to solve translation tasks, because they are based on phrases and this leads to our model can't capture the difference between languages.
We can solve this problem by using **Seq2Seq** architecture especially with using the [**LSTMs**](https://manishemirani.github.io/Long-Short-Term-Memory/) in this 
architecture.

# Seq2Seq

**Sequence-to-Sequence**(Seq2seq) is a model that made up of two recurrnet neural networks.

1 - **Encoder** -> This layer takes a sentence from the source language and encodes it into a 'context vector'

2 - **Decoder** -> This layer takes a context vector(which is come from encoder output) as an initializer hidden state and starts predicting the target language words with knowing the information from source language

|![_config.yml]({{ site.baseurl }}/images/Machine Translation/seq2seq.gif)|
|:--:| 
| Figure 2 : Seq2Seq model|

This architecture has a problem. The problem is that all pieces of information about the source sentence are store in a single vector(context vector). In another word for each step in RNNs the previous hidden state add to the current hidden state with some forgotten information from previous hidden state and that means, in the context vector we kinda have a summarization of previous hidden states. This problem calls the **bottleneck problem**.

How could we solve this problem? well, the short answer is **Attention Mechanism**

# Attention Mechanism

Attention Mechanism enables the decoder network to look at the entire input sentence at every decoding step. Then the decoder can decide what input words are important at every time step for predicting the next words.
In practice, we find similarities between all hidden states in the encoder and each time step in the decoder with the [dot product](https://en.wikipedia.org/wiki/Dot_product) between those. At the end of this operation, we have some **Attention scores**. Then feed these attention scores to **[softmax function](https://en.wikipedia.org/wiki/Softmax_function)** to receive attention distribution and multiply these probabilities to the encoder hidden state to define which hidden state in the encoder is more important for the decoder in each time step and add these vectors together to achieve **context vector**.

[![steps](https://res.cloudinary.com/marcomontalbano/image/upload/v1629983536/video_to_markdown/images/video--a23b083158c1d21b3d4d045f1e0d92e5-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://jalammar.github.io/images/attention_process.mp4 "steps")

## Attention mechanism in equation

Asume that we have **'n'** hidden states in encoder **h_1**, **h_2**, ...., **h_n** and on timestep **'t'** we have decoder hidden state **s_t**. we get attention scores with this formula:

|![_config.yml]({{ site.baseurl }}/images/Machine Translation/att_scores_formula.png)|
|

Then give the result to softmax function to get the attention distribution:

|![_config.yml]({{ site.baseurl }}/images/Machine Translation/softmax_att.png)|

Multiply the hidden state to attention probibalities and sum up the weighted vectors:

|![_config.yml]({{ site.baseurl }}/images/Machine Translation/add.png)|

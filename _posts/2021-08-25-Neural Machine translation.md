---
published: true
---
Machine Translation(MT) is a task that can translate a sentence X from one language(the source language) to a sentence Y from another language(the target language).

|![_config.yml]({{ site.baseurl }}/images/Machine Translation/MT_ex.png)|
|:--:| 
| Figure 1 : English to Germany|

In the past translation system were based on two parts:

1 - Translation model -> Defines what sentence/phrase in the source language is most likely to the target language sentence/phrase.

2 - Language model -> Defines the probability of each sentence/phrase could occur

But these models are not good enough to solve translation tasks, because they are based on phrases and this leads to our model can't capture the difference between languages.
We can solve this problem by using **Seq2Seq** architecture especially with using the [**LSTMs**](https://manishemirani.github.io/Long-Short-Term-Memory/) in this 
architecture.
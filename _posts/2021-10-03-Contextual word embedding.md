---
published: false
---
One of the problems in the NLP is that the ordinary pre-trained word embeddings haven't contained the information about the context of each word in a specific sentence. For instance, if we have a sentence like "Your mouse likes cheese" and "Buy a new mouse for computer" and use ordinary embedding for the word "mouse" we will get the same word embedding vector for both. In contextual word embedding, the goal is that to have a different word embedding vector for each word in a specific situation.

|![_config.yml]({{ site.baseurl }}/images/BERT/problem_sentence.png)|
|:--:| 
| Figure 1: Same word embedding|

|![_config.yml]({{ site.baseurl }}/images/BERT/solution.png)|
|:--:| 
| Figure 1: Contextual word embedding|

---
published: true
---
Long Short-Term Memory(LSTM) is a kind of RNNs which is using different architecture from other RNNs to prevent Vanishing Gradient and have a longer memory. But before explaining LSTMs let's look at the traditional RNN architecture.

|![_config.yml]({{ site.baseurl }}/images/LSTM/RNN.png)|
|:--:| 
| Figure 1 : RNN architecture|

As you can see in Figure 1 there is no mechanism to deliver the hidden memory vector to other time steps. In another word data from each time step is replacing with the past time step data and input data, so the hidden memory affects on few time steps 
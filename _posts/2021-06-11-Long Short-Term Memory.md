---
published: true
---
Long Short-Term Memory(LSTM) is a kind of RNNs which is using different architecture from other RNNs to prevent Vanishing Gradient and have a longer memory. But before explaining LSTMs let's look at the traditional RNN architecture.

|![_config.yml]({{ site.baseurl }}/images/LSTM/RNN.png)|
|:--:| 
| Figure 1 : RNN architecture|

As you can see in Figure 1 there is no mechanism to deliver the hidden memory(h) vector to other time steps. In other words data from each time step is replacing with the past time step data and input data, so the hidden memory affects few time steps. In LSTMs we have new gates that can help us to solve this problem.

# Model Architecture

|![_config.yml]({{ site.baseurl }}/images/LSTM/model.png)|
|:--:| 
| Figure 2 : LSTM architecture|

LSTM Gatest:

1 - Forget gate

2 - Update gate(also called input gate)

3 - Output gate

In addition to these gates, we have a new parameter which is Memory Cell(C). LSTMs have two outputs, one is h_t and another one is c_t.

## Forget Gate


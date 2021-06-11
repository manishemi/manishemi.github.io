---
published: true
---
Long Short-Term Memory(LSTM) is a kind of RNNs which is using different architecture from other RNNs to prevent Vanishing Gradient and have a longer memory. But before explaining LSTMs let's look at the traditional RNN architecture.

|![_config.yml]({{ site.baseurl }}/images/LSTM/RNN.png)|
|:--:| 
| Figure 1 : RNN Architecture|

As you can see in Figure 1 there is no mechanism to deliver the hidden memory(h) vector to other time steps. In other words data from each time step is replacing with the past time step data and input data, so the hidden memory affects few time steps. In LSTMs we have new gates that can help us to solve this problem.

# Model Architecture

|![_config.yml]({{ site.baseurl }}/images/LSTM/model.png)|
|:--:| 
| Figure 2 : LSTM Architecture|

LSTM Gates:

1 - Forget gate

2 - Update gate(also called input gate)

3 - Output gate

In addition to these gates, we have a new parameter which is Memory Cell(C). LSTMs have two outputs, one is h_t and another one is c_t.

## Forget Gate

Assume that we a data(h_t) that changed from h_t-1 so we should replace the h_t-1 with a new 
value, we use forget gate for that reason

|![_config.yml]({{ site.baseurl }}/images/LSTM/forget_gate.png)|

W_f is a weight matrix that controls the Forget gate behavior. we stacked the h_t-1 and X_t and then multiply it to W_f matrix, then giving the result  to [sigmoid fucntion](https://en.wikipedia.org/wiki/Sigmoid_function) and getting output between 0 and 1([0, 1]), sigmoid function defines that how much should use the previous cell.

|![_config.yml]({{ site.baseurl }}/images/LSTM/lstm1.gif)|

## Update Gate

After forgetting the previous cell, now it's time to update our new cell:

|![_config.yml]({{ site.baseurl }}/images/LSTM/update_gate.png)|

Now we need a new vector:

|![_config.yml]({{ site.baseurl }}/images/LSTM/C.png)|

We add our new vector to previous cell with:

|![_config.yml]({{ site.baseurl }}/images/LSTM/add_update.png)|

Update gate:

|![_config.yml]({{ site.baseurl }}/images/LSTM/lstm2.gif)|

## Output Gate

At the end, Output gate desines that what value should use for hidden memory

|![_config.yml]({{ site.baseurl }}/images/LSTM/output_gate.png)|

And then:

|![_config.yml]({{ site.baseurl }}/images/LSTM/final_output.png)|



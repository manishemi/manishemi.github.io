---
published: true
---
If you have ever seen the transformers movie series you should probably saw, how they are transforming from a car to a robot or vice versa. Transformer in machine learning is similar to them

The best performing models also connect the encoder and decoder through an attention mechanism. 
Also,  the Transformers based solely on attention mechanism and encoder-decoder architecture

### Background

Self-attention(sometimes called intra-ttention) is an attention mechanism relating different position of single sequence in order to compute a representation of the sequence

Tranformer is the first transduction model relying entirely on self-attention without using RNNs or 
convolution 

### Model Architecture
Generally, Transformer mades with encoder-decoder architecture but inside the encoder and decoder we have
some operation


|![_config.yml]({{ site.baseurl }}/images/Transformers/Model_Architecture.PNG)|
|:--:| 
| *Figure 1 : Tranformer - Model Architecture* |


Encoder: The encoder is composed of a stack of N identical layers. Each layer has two sub-layer, 
one is a multi-head self-attention mechanism and the second one is a fully connected feed-forward network.

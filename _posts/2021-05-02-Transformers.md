---
published: true
---
If you have ever seen the transformers movie series you should probably saw, how they are transforming from a car to a robot or vice versa. Transformer in machine learning is similar to them

The best performing models also connect the encoder and decoder through an attention mechanism. 
Also,  the Transformers based solely on attention mechanism and encoder-decoder architecture

### **Background**

Self-attention(sometimes called intra-attention) is an attention mechanism relating different position of single sequence in order to compute a representation of the sequence

Tranformer is the first transduction model relying entirely on self-attention without using RNNs or 
convolution 

### Model Architecture
Generally, Transformer mades with encoder-decoder architecture but inside the encoder and decoder we have
some operation


|![_config.yml]({{ site.baseurl }}/images/Transformers/Model_Architecture.PNG)|
|:--:| 
| *Figure 1 : Tranformer - Model Architecture* |


#### **Encoder**:
The encoder is composed of a stack of N identical layers. Each layer has two sub-layer, 
one is a multi-head self-attention mechanism and the second one is a fully connected feed-forward network.
In addition after each layer, we have a layer normalization which normalizes the output of the previous layer.

In another word, the output of each sub-layer is LayerNorm(x + Sublayer(x)) where Sunblayer(x) is a function implemented by the sub-layer itself (for instance: multi-head attention or feed-forward network)

Normalization:

|![_config.yml]({{ site.baseurl }}/images/Transformers/Normalization_formula.PNG)|
|:--:| 
| Figure 2 : Normalization Formula|

x = Input

μ = Mean of x

σ = Standard deviation of x ---> sqrt(sum((x[i] - mean) ** 2 for i in range(len(x)) / len(x))

z = Normalized output

#### **Decoder**: 
The decoder also is composed of a stack of N identical layers. It has two sub-layer in each encoder layer, the decoder inserts a third sub-layer, which performs multi-head attention over the output of the encoder stack. Similar to the encoder, the decoder has layer normalization.

In the third sub-layer, we have a different form from another attention mechanism which is the masking method, it ensures that prediction for position i can depend on the known outputs at positions less than i

#### **Attention**:
An attention function can be described as mapping query and a set of key-value pairs to an output,
where the query, keys, values, and output are all vectors.

The output computed as a weighted sum of the values, where the weight assigned to each value (how much attention should pay for this value)




























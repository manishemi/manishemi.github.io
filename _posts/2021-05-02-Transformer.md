---
published: true
---
If you have ever seen the transformers movie series you should probably saw, how they are transforming from a car to a robot or vice versa. Transformer in machine learning is similar to them

The best performing models also connect the encoder and decoder through an attention mechanism. 
Also,  the Transformers based solely on attention mechanism and encoder-decoder architecture

### _**Background**_

Self-attention(sometimes called intra-attention) is an attention mechanism relating different position of single sequence in order to compute a representation of the sequence

Tranformer is the first transduction model relying entirely on self-attention without using RNNs or 
convolution 

### _**Model Architecture**_
Generally, Transformer mades with encoder-decoder architecture but inside the encoder and decoder we have
some operation


|![_config.yml]({{ site.baseurl }}/images/Transformers/Model_Architecture.PNG)|
|:--:| 
| *Figure 1 : Tranformer - Model Architecture* |


#### _**Encoder**_:
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

#### _**Decoder**_: 
The decoder also is composed of a stack of N identical layers. It has two sub-layer in each encoder layer, the decoder inserts a third sub-layer, which performs multi-head attention over the output of the encoder stack. Similar to the encoder, the decoder has layer normalization.
In the third sub-layer, we have a different form from another attention mechanism which is the masking method, it ensures that prediction for position i can depend on the known outputs at positions less than i.

#### _**Attention**_:
An attention function can be described as mapping query and a set of key-value pairs to an output,
where the query, keys, values, and output are all vectors.
The output computed as a weighted sum of the values, where the weight assigned to each value (how much attention should pay for this value)

#### _**Scaled Dot Product Attention**_:

|![_config.yml]({{ site.baseurl }}/images/Transformers/Scaled_Dot_Product_Attention.PNG)|
|:--:| 
| Figure 2 : Scaled Dot Product Attention|


The inputs consist of queries and keys with dimension dk and values with dimension dv.
for scaled dot product attention implement we compute dot product with query with all keys divide by
√dk and then apply softmax function to obtain weights 

|![_config.yml]({{ site.baseurl }}/images/Transformers/Attention_Formula.PNG)|

Why √dk?

#### **_Provided by article_**:

We suspect that for large values of
dk, the dot products grow large in magnitude, pushing the softmax function into regions where it has
extremely small gradients . To counteract this effect, we scale the dot products by (1 / √dk)

To illustrate why the dot products get large, assume that the components of q and k are independent random
variables with mean 0 and variance 1. Then their dot product has mean 0 and variance dk


#### _**Multi Head Attention**_:

Multi head attention allows the model to jointly attend to information from diffrent representation

|![_config.yml]({{ site.baseurl }}/images/Transformers/Multi_Head_Attention_Formula.PNG)|

#### _**Feed-Forward Networks**_:

The Feed-Forward networks consist of two fully-connected layers with ReLU activation in between.

|![_config.yml]({{ site.baseurl }}/images/Transformers/Feed_Forward.PNG)|

For implementation you can also visit [Transformer model for language understanding](https://www.tensorflow.org/tutorials/text/transformer)
They've implemented Transformer with TensorFlow,  I suggest implementing a transformer with python for a better understanding of the concept

#### _**Positional Encoding**_:

Since this model doesn't contain any recurrence or convolution, positional encoding is added to give the model some information of the relative positions of the words in the sentence.
The positional encoding vector is added to the embedding vector.

|![_config.yml]({{ site.baseurl }}/images/Transformers/Positional_Encoding.PNG)|

pos = Positional

i = Dimension

d_model = Dimension of model

# _**References**_:
[Trasformer Article](https://arxiv.org/abs/1706.03762)

[Tensorflow](https://www.tensorflow.org/tutorials/text/transformer)

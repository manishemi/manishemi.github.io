---
published: true
---
Deep Convolutional GAN is a kind of [GAN](https://manishemirani.github.io/Generative-Adversarial-Networks/) network, which is using Convolution network in the Discriminator and Convolution transpose network in the Generator.


# How are the Convolutions network work?
Convolution networks are based on the Convolution layers which have trainable filters. These filters(matrices) have a smaller dimension than input data(input matrices), they multiply to input data and create an output that has less dimension of the input matrix.

|![_config.yml]({{ site.baseurl }}/images/DCGANs/1_ZCjPUFrB6eHPRi4eyP6aaA.gif)|
|:--:| 
| Figure 1 : Filters , yellow is a filter(kernel)|


Filters(kernels) have two base part:

1 - Size, which defines kernel size(e.g 3×3)

2 - Strides, which defines step per each multiply(in Figure 1 it's 1, steps start from the center of each kernel)

## Pooling Layer

The pooling layer decreases the dimension of Convolution layers. This layer leads to prevents overfitting and decreasing computation.

We have three kinds of pooling layer:

1 - Max Pooling

2 - Average Pooling

3 - Sum Pooling

|![_config.yml]({{ site.baseurl }}/images/DCGANs/pooling.gif)|
|:--:| 
| Figure 2 : Kinds of pooling layers|

Parameters in the Pooling layer are as same as the Convolution layer

### NOTE: The Discriminator uses this kind of Convolution layer


### But how about the Generator?

The Generator uses Transpose Convolution network

# How are the Transpose Convolutions network work?

Imagine we have a input like this:

|![_config.yml]({{ site.baseurl }}/images/DCGANs/input_matrix.png)|
|:--:| 
| Figure 3 : shape 4×4|


And a kernel like this:

|![_config.yml]({{ site.baseurl }}/images/DCGANs/kernel.png)|
|:--:| 
| Figure 4 : shape 3×3|


The Convolution matrix would be:

|![_config.yml]({{ site.baseurl }}/images/DCGANs/cnv_matrix.png)|
|:--:| 
| Figure 5 : shape 4×16|


Reult:

|![_config.yml]({{ site.baseurl }}/images/DCGANs/multiply.png)|
|:--:| 
| Figure 5 : shape 4×1, input matrix is flatten|

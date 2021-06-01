---
published: true
---
Deep Convolutional GAN is a kind of [GAN](https://manishemirani.github.io/Generative-Adversarial-Networks/) network, which is using Convolution network in the Discriminator and Convolution transpose network in the Generator.


# How are the Convolution networks work?
Convolution networks are based on the Convolution layers which have trainable filters. These filters(matrices) have a smaller dimension than input data(input matrices), they multiply to input data and create an output that has less dimension of the input matrix.

|![_config.yml]({{ site.baseurl }}/images/DCGANs/1_ZCjPUFrB6eHPRi4eyP6aaA.gif)|
|:--:| 
| Figure 1 : Filters, yellow is a filter(kernel)|


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

# How are the Transpose Convolution networks work?

Assume that we have an input like this:

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


Result:

|![_config.yml]({{ site.baseurl }}/images/DCGANs/multiply.png)|
|:--:| 
| Figure 6 : shape 4×1, input(Figure 3) matrix is flattened |

This operation is for the Convolution layer. In Transpose Convolution, we transpose the Convolution matrix and then multiply it to the input matrix

|![_config.yml]({{ site.baseurl }}/images/DCGANs/transposed conv.png)|
|:--:| 
| Figure 7 : Transposed Convolution matrix, shape 16×4|


Shape from Figure 6 is 4×1 or 2×2, if we want to have an output with shape 16×1 or 4×4 we should multiply  Transposed Convolution matrix to flatten the input, which means we have a larger output so now The Generator can generate data

# Implementation
For implementation, you can also visit my [github page](https://github.com/manishemirani/Simple_GAN)
or visit [Tensorflow](https://www.tensorflow.org/tutorials/generative/dcgan)

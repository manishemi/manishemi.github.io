---
published: true
---
Deep Convolutional GAN is a kind of [GAN](https://manishemirani.github.io/Generative-Adversarial-Networks/) networks, which is using Convolution network in the Discriminator and Convolution transpose network in the Generator.


# How are the Convolutions network work?
Convolution networks are based on the Convolution layer which has trainable filters. These filters(matrices) has a smaller dimension than input data(input matrices), they multiply to input data and create an output that has less dimension of the input matrix.

|![_config.yml]({{ site.baseurl }}/images/DCGANs/1_ZCjPUFrB6eHPRi4eyP6aaA.gif)|
|:--:| 
| Figure 1 : Filters , yellow is a filter(kernel)|


Filters(kernels) have two base part:

1 - Size, which defines kernel size(e.g 3×3)

2 - Strides, which defines step per each multiply(in Figure 1 it's 1, steps start from the center of each kernel)

## Poolling Layer


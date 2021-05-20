---
published: true
---
I've heard about a kind of Neural network that can generate data from a specific dataset. I've been curious that how they are work?, so I've read about them and saw they have interesting architecture.

Genrative Adversarial network(GAN) is a Nerual network model that generate sample like dataset features from random input(noise vector).

GANs have two base part:

1 - Generator network

2 - Discriminator network

|![_config.yml]({{ site.baseurl }}/images/GANs/GAN figure.png)|
|:--:| 
| Figure 1 : GAN Architecture |


Note that: Generative and Discriminator are based on Neural networks

Training task is based on [Backpropagation algorithm](https://en.wikipedia.org/wiki/Backpropagation) and the loss from the Discriminator network(cost function)

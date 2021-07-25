---
published: true
---
Vanishing gradient is a problem that happens when the training method in Neural networks is based on gradient. In this method, the gradient is used for updating parameters in Neural networks, each parameter is changed for the amount of effect that it has on the final result in the Neural networks.

Vanishing gradient problem referring that the amount of gradient is gradually reduced when the gradient goes to the beginning of the neural network and that leads to reduce the training time(because the weight change is insignificant)

|![_config.yml]({{ site.baseurl }}/images/V-E-Gradient/Vanishing_Gradient.png)|
|:--:| 
| Figure 1 : Vanishing Gradient |

### What is the cause of the vanishing gradient in the recurrence neural networks?

Assume that we have a sentence like "I am interested in ML, AI and one day I will create a machine like a human" ( just for example :) ) that has 17 words. When our model can predict the last word
(human) correctly that it has information about the first word(I). We call this kind of dependencies,
Long-Term Dependencies.

In practice, if we have more distance between our first and last words, then we have a vanishing gradient problem. Because the gradients come from the end of layers, they should pass many multiplications until they arrive at the beginning layers and that leads to having small gradients (less than 1).

### How we can solve this problem?

Using [LSTM](https://manishemirani.github.io/Long-Short-Term-Memory/) or GRU(they are made for that reason)

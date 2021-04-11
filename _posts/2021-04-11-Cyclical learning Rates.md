---
published: true
---
The cyclical learning rate(CLR) is a method for setting the learing rates, which practically find the best values and schedule for the global learning rates.

This method sets minimum and maximum boundaries and the learning rate cyclically varies between these.

![_config.yml]({{ site.baseurl }}/images/CLR/1.PNG)


This curve shows the result of CLR method using on CIFAR-10

![_config.yml]({{ site.baseurl }}/images/CLR/2.PNG)

## Implementation

# Provided by article
For the implementation we should have some parameters of our model:
![_config.yml]({{ site.baseurl }}/images/CLR/3.PNG)

    1 - epochCounter --> the number of epoch training 

    2 - stepsize --> Half of the cycle lenght

	3 - max_lr --> Maximum learning rate schedule
	
    4 - min_lr --> Minimum laerning rate schedule




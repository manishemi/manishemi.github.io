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

![_config.yml]({{ site.baseurl }}/images/CLR/3.PNG)

    1 - epochCounter --> Number of epochs of training 

    2 - stepsize --> Half of the cycle lenght

	3 - max_lr --> Maximum learning rate schedule
	
    4 - min_lr --> Minimum laerning rate schedule
    
    
# Implementation with python

```python

def create_traingular_schedule(lr_min, lr_max, step_per_cycle):
top = (step_per_cycle + 1) // 2
    def learning_rate_fn(step):
    	cycle_step = step % step_per_cycle
        if cycle_step < top:
        	lr = lr_min + (cycle_step / top) * (lr_max - lr_min)
        else:
            lr = lr_max - ((cycle_step - top) / top) * (lr_max - lr_min)
        return lr
    return learning_rate_fn
```

Parameters:
	
step_per_cycle --> Part of step_per_epochs(step_per_epochs is the output of training data length divided by 		batch size) 
    
step --> The output of of optimizer.state.step for more information click				
    [here](https://flax.readthedocs.io/en/latest/howtos/lr_schedule.html)
    
    
# References:

[Cyclical learning Rate Article](https://arxiv.org/abs/1506.01186)

[Flax](https://flax.readthedocs.io/en/latest/howtos/lr_schedule.html)

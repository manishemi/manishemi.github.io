---
published: true
---
Reinforcement Learning(also called **RL**) is another learning algorithm that can learn to act appropriately in a specific environment. The **RL** algorithm is based on five parts.

|![_config.yml]({{ site.baseurl }}/images/RL/RL_fig1.jpg)|
|:--:| 
| Figure 1: RL parts|


## _Parts_

1 - **Agent**: An agent is an actor in the environment that can take actions, for instance as you can see in Figure 1 the dog is an agent

2 - **Environment**: Environment is a place that the agent exists and operates

3 - **Actions**(Action space): Action space is a set of possible actions that the agent can make(The action space can be discrete or continuous)

4 - **Observation**: Observation is how the Environment interact back with the Agent and the agent can observe where Environment is and how its action affected the Environment

5 - **Reward**: Reward is a scale for the success or failure of an agent's action. For example, if the dog(Agent) returns the bone will take food,  otherwise won't take anything

We have also two kinds of a learning algorithm in RL:

1 - _**Value Learning**_

2 - _**Policy Learning**_

But before explaining learning algorithms let's see what is **Q-Function** and how is it work?

## _Q-Function_

The Q-function is a function that captures the expected total future reward an agent in the state(s) can receive by executing a certain action(a)

|![_config.yml]({{ site.baseurl }}/images/RL/q_function.png)|
|:--:| 
| Figure 2: Q-function|

**State**: A state is a situation that the agent perceives

**Total Reward**(also called return): The total reward is a summation of discounted rewards. The discounted reward defines that the reward that the agent receives in time **t** is more important than time **t + 1**, the discount factor is a number between 0 and 1 **(0 < γ < 1)**

|![_config.yml]({{ site.baseurl }}/images/RL/discounted_reward.png)|
|:--:| 
| Figure 3: Discounted Reward|


## _Value Learning_

|![_config.yml]({{ site.baseurl }}/images/RL/pv.png)|
|:--:| 
| Figure 4: Value Learning|


In Value learning the approach is that find maximum **Q-value** from a specific state. Since is very hard for a human to compute the Q value,  we use aneural networks to achieve 
**Q-values** and then select the maximum **Q-value** and then select the action from max Q-value and send it back to enviromment for receive next state

|![_config.yml]({{ site.baseurl }}/images/RL/DQN.png)|
|:--:| 
| Figure 5: Deep Q Network|



## _Policy Learning_


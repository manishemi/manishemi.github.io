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

5 - **Reward**: Reward is a scale for the success or failure of an agent's action. For example, if the dog(Agent) returns the bone will take food,  otherwise won't take food

We have also two kinds of a learning algorithms in RL:

1 - _**Value Learning**_

2 - _**Policy Gradient**_

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


In Value learning the policy is that find maximum **Q-value** from a specific state. Since is very hard for a human to compute the Q value,  we use Neural networks to achieve 
**Q-values**, then select the maximum **Q-value**, select the action from the maximum Q-value and return it to the environment for receiving the next state.

|![_config.yml]({{ site.baseurl }}/images/RL/DQN.png)|
|:--:| 
| Figure 5: Deep Q Network|

### Downside of value learning

You can not use this algorithm for continuous action space, It's for discrete and small action space. 

## _Policy Gradient_

Policy Gradient(PG) enables the modeling of continuous action space. which can give us an appropriate action rather than Q-value for a specific state.

|![_config.yml]({{ site.baseurl }}/images/RL/policy.png)|
|:--:| 
| Figure 6: PG Architecture|

### Loss

|![_config.yml]({{ site.baseurl }}/images/RL/pg_loss.png)|
|:--:| 
| Figure 7: PG loss|

As you can see in Figure 7 we use total reward(return) to compute the loss. If the agent gets a high reward then the paraments will change a little because they perform well.

_**Gradient descent**_:

|![_config.yml]({{ site.baseurl }}/images/RL/pg_grad.png)|
|:--:| 
| Figure 8: PG gradient|


## Examples

For RL examples you can visit the [gym](https://gym.openai.com/), they have pre-built [environments](https://gym.openai.com/envs/) and agents. All you have to do is implement a learning algorithm. I've solved a problem call [Copy-v0](https://gym.openai.com/envs/Copy-v0/) in my [Github page](https://github.com/manishemirani/Copy-v0) as well


# Refrence:
[MIT deep learning](http://introtodeeplearning.com/)
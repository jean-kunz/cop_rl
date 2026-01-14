# Reinforcement learning

## Sources
https://medium.com/@lgendrot/teaching-myself-reinforcement-learning-7b4157ee3b68



![alt text](image.png)

## Observations
Agents need to get information about the environment in order to make decisions on how to act. In the Atari example the observations might amount to screenshots of the game being played, the same as a human would see

## Agents
The agent receives observations of the environment, and uses those observations to select actions, which affects the environment and ultimately causes a reward signal to be given to the agent.


## States and the Markov Property
In the course of operation, the agent generates a “path” through an environment, which consists of sequential sets of observations, rewards, and next actions for each step the agent takes.

The history of an agent/environment pair includes all of the observations, rewards, and actions generated up to a particular point in time. 

![](image-2.png)

It’s unnecessary to store the entire history of an agent -> concept of state. The state is formally just a function that produces a summary of the history up to a certain point.

![](image-3.png)

The state can be thought of from both the perspective of the environment (environment state) and the agent (agent state, built entirely by the developer and by the algorithm used to solve the reinforcement learning problem.).

Ideally any state, being a summary of the history, would contain all the useful information about the history

![alt text](image-1.png)

**fully observable** environment, the agent state is the same as the environment state.

**partially observable** environment the agent state must be somehow computed from the history, since the observations are now incomplete representations of the environment


## Anatomy of a Reinforcement Learning Agent

![alt text](image-4.png)


![](image-5.png)

**Stochastic policy** outputs a probability distribution over actions which can be sampled from, again given a state

### Value function
![alt text](image-6.png)

Estimate of how much future reward the agent can expect to receive if it is governed by our current policy.

Parameterized by a **discount** factor (gamma in the above formula)

## Model

“What’s going to happen next if I do this?”

Agent’s learned conception of how the environment works. Given a particular state and an action to take, the agent’s model will give it a prediction of the next state

Can also predict the reward given a state and action pair.

![alt text](image-7.png)

## Categories of agents

![alt text](image-8.png)

**policy based**, learning a policy directly without learning a value function.

**value based**, where it has no explicit policy, but instead learns a value function and acts based on its estimates. (Technically it still has an implicit policy: choose the best action).

**actor-critic**, having both a learned policy and an estimated value function for that learned policy.



-----
Tabular data about state,... vs non tabular data
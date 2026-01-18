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

## MDP
MDP, or Markov Decision Process : is the main formalism used in Reinforcement Learning


**fully observable MDPs** :  the current state that is given to the agent completely characterizes the environment. So the way in which the environment unfolds depends on some state, and we are told that state.”

**partially observed** can be converted to MDP and so behave largely the same way

Starting with:
Markov Chains >> Markov Reward Processes >>  Markov Decision Processes

### Markov chains
![alt text](image-9.png)

We don’t need to know the full history of states to know what will happen next, just the current one

State transition matrix, probability of transition from a state (row) to another one (col):
![alt text](image-10.png)

A Markov Chain has **no rewards or actions yet**, it simply defines a random process that generates a set of states, each with the Markov property

![alt text](image-11.png)

Student MDP:

![alt text](image-12.png)

On can generate random set of states. Ex: ```['C1', 'C2', 'C3', 'Pub', 'C1', 'C2', 'Sleep']````
Agent make no decision, only at mercy of chance.  

### Markov Reward Processes
A Markov reward process is exactly like a Markov chain, except each step taken generates a reward.

![](image-13.png)

![alt text](image-14.png)

trajectories we sample will have an associated return value.

![alt text](image-15.png)

Gamma (0..1) determines how important future rewards are to the agent. if close to 0, consider immediate reward only.

Gamma=1 (for the rest of course for convenience)

Value function: expectation over future rewards 

![](image-16.png)

Thanks to the law of large numbers, a rough estimate of the true value function for a state can be achieved by sampling many trajectories starting from that state, and averaging the sampled returns


### Bellman equation



![alt text](image-17.png)

as gamma is constant:
![alt text](image-18.png)
![](image-19.png)


![alt text](image-20.png)

So : **value of a state s is the expectation over the immediate reward plus the discounted expected future reward***




-----
Tabular data about state,... vs non tabular data
# Udacity DRL nanodegree - Project 2: Continuous Control
In this project, we train a double-jointed arm to move to target locations.
The environment is provided by a Unity machine learning agent called Reacher. More information on the Unity ml-agents can be found [here](https://github.com/Unity-Technologies/ml-agents).

## Project Details
The agent interfaces to an environment which is characterised as follows:

A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

The task is episodic, and in order to solve the environment, your agent must get an average score of +30 over 100 consecutive episodes.

### Repository structure
The code is structured as follows: 
* **Continuous_Control.ipynb**: this is where the deep rl agent is trained. The agent is structured according to the DDPG actor critic algorithm, details of which can be found [here](https://arxiv.org/pdf/1509.02971.pdf).
* **ddpg_agent.py**: this module implements a class to represent a vanilla ddpg agent.
* **model.py**: this module contains the implementation of the actor and critic neural networks. The actor is the policy approximator which provides the critic with the best action vector to take at each time step. The critic is the action value function approximator and its aim it to approximate the optimal action value function.
* **checkpoint_actor.pth**: this is the binary containing the trained actor neural network weights.
* **checkpoint_critic.pth**: this is the binary containing the trained critic neural network weights.
* **Reacher_Windows_x86_64**: this directory contains the binary for the Reacher environment utilised in this project. It's for running on Windows 10, 64-bit.

### Dependencies
* python 3.6
* numpy: install with 'pip install numpy'.
* PyTorch: install by following the instructions [here](https://github.com/reinforcement-learning-kr/pg_travel/wiki/Installing-Unity-ml-agents-on-Windows).
* ml-agents: install by following instructions [here](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Installation-Windows.md).

## Getting Started
In cell 2 of Continuous_Control.ipynb we import the binary for the Unity environment 'Reacher.exe'. For a local installation of the Unity ml-agents, please refer to the following two sources:
* [Linux, Mac](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Installation.md)
* [Windows 10](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Installation-Windows.md)

## Instructions
This is a jupyter notebook project. To run the code and train the deep reinforcement learning agent, you simply execute each of the cells in **Continuous_Control.ipynb**. After training, the average score per hundred episodes will be displayed and a plot of the score per episode will also be shown.
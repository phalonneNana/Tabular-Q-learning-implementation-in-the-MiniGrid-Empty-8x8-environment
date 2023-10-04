# Goal
This work presents the implementation and evaluation of Tabular Q-Learning and SARSA algorithms in the MiniGrid- Empty-8x8 environment. The goal is to develop agents capable 
of efficiently navigating a grid and reaching a specified goal by learning from observed states. 
In order to implement a Q-learning algorithm, there are a couple of preliminaries to understand, including:

the gridworld environment,
the action space of the agent,
the reward signal


# Gridworld Environment
The gridworld environment we will be using was written by Maxime Chevalier-Boisvert and can be obtained from Github: https://github.com/Farama-Foundation/gym-minigrid

This environment is an empty room, and the goal of the agent is to reach the green goal square, which provides a sparse reward. A small penalty is subtracted for the number 
of steps to reach the goal. This environment is useful, with small rooms, to validate that our RL algorithm works correctly, and with large rooms to experiment with sparse 
rewards and exploration. The random variants of the environment have the agent starting at a random position for each episode, while the regular variants have the agent always 
starting in the corner opposite to the goal.

# Structure of the world:
* The world is an NxM grid of tiles
* Each tile in the grid world contains zero or one object
* Cells that do not contain an object have the value None
* Each object has an associated discrete color (string)
* Each object has an associated type:
- 'unseen' : 0
- 'empty' : 1
- 'wall' : 2
- 'floor' : 3
- 'door' : 4
- 'key' : 5
- 'ball' : 6
- 'box' : 7
- 'goal' : 8
* The agent can pick up and carry exactly one object (eg: ball or key)
* To open a locked door, the agent has to be carrying a key matching the door's color

# Actions in the basic environment:
The environment defines the following basic actions that the agent can perform each step:``

* Turn left
* Turn right
* Move forward
* Pick up an object
* Drop the object being carried
* Toggle (open doors, interact with objects)
We will only be using the first three actions, i.e. "Turn left", "Turn right" and "Move forward".

# Result
Through hyperparameter tuning using grid search, both algorithms were trained and evaluated based on completion rate, average number of steps, and aver- age reward. 
The results indicate that Q-Learning outperforms SARSA with slightly better average number of steps and reward, demonstrating its effectiveness in finding optimal paths. 
However, both algorithms achieve a 100% completion rate, indicating their success in reaching the goal. These findings contribute to the understanding and application of 
reinforcement learning algorithms in grid-based environments, offering potential for further exploration and improvement in autonomous navigation and decision-making.

# GOOD READING :)



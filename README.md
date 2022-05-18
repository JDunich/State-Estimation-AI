# State-Estimation-AI

This repository contains code for a state estimation Algorithm which predicts an agents location given its recoded transitions and obervations.

Before the algorithms is ran, 100 x 50 state space grids are generated with each cell receiving a label from [B, H, T, N]. Given the grid layout, an agent is placed randomly and preforms 100 random moves, observing the cell it is standing on after each move.

The transiton model for the agent passes 90% of the time (the agent moves) and fails 10% of the time (the agent says it moves but doesnt). The observation model for the agent passes 90% of the time (records the current cell correctly) and fails 10% of the time with a 5% chance it records one of the other two possible cells. 

After the agent takes 100 random actions, the 100 observations, 100 actions, and 100 true location coordinates are saved to a file. The whole process of dropping an agent in randomly and having it preform 100 actions is done 10 times per map, with 10 maps in total. 

Now it's time to use the State Estimation. By taking a map and a file recodring of an agents 100 actions and observations in that map, I am able to create a heatmap of the probability of the agent being in each cell at a specific timestamp without knowing where the agent originally started. 

We can look through how the algorithm handles the first saved actions of the agent in the first state map. 

After the agent preforms 100 random movements on the state space, the following file is saved [action_file]()

We can then feed the state estimation algorithm this action_file along with the original state space and we are left with the following statistics. 


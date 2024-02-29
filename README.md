![ubern winter school banner](image.png)

_See [Reinforcement Learning Goes Deep (Part I): Q-learning Algorithm Implementation for a Grid World Environment](https://heseltime.github.io/rDai#rl-1) also for a summary blog post about this content from [uBern Winter School](https://www.dsl.unibe.ch/training/winter_schools/) on Reinforcement Learning this February_

## Test Project: Environment, Policy, and the OpenAI Gym

The provided code is an implementation of the Q-learning algorithm tailored for a specific grid world environment. This environment includes an agent, an enemy, and a target, all located within a grid. The goal of the Q-learning algorithm is to learn an optimal policy for the agent to navigate the grid to reach the target while avoiding the enemy.

![Sample Successful Run with Blind Enemy](../assets/video/sample_successful_run_RL_post.mp4)



https://github.com/heseltime/reinforcement-learning-ubern/assets/66922223/4bd2dca4-673d-43bb-b48b-ec27775a8534



### Key Components

* Initialization and Episode Loop: The run_episode_gwenv function initializes the episode by resetting the environment, which provides the initial state. The episode then runs for a maximum number of steps defined by _maxsteps, simulating the agent's interactions within the environment.
* State Representation: States are represented by the grid positions of the agent, enemy, and target. This requires a multidimensional Q-table to accommodate the multi-entity state space.
* Epsilon-Greedy Policy: During training, an epsilon-greedy policy is employed for action selection. This involves choosing a random action with a probability of epsilon (exploration) and the best-known action with a probability of 1 - epsilon (exploitation).
* Q-Table Update: The Q-value for the taken action is updated using the observed reward and the maximum Q-value of the next state, adjusted by the learning rate lr and discounted by the factor discount. This update mechanism is guided by the Bellman equation.
* Parameters:
    * lr/alpha: Learning rate, controlling the Q-value update magnitude. (In the group at uBern my group focused on varying this parameter, hence the multiple versions at the end of [**Control.ipynb**](https://github.com/heseltime/reinforcement-learning-ubern/blob/main/Control.ipynb))
    * discount/gamma: Discount factor, influencing the weight of future rewards.
    * epsilon: Exploration-exploitation trade-off parameter.
* Optimal Policy Execution: If the optimal flag is true, the algorithm solely relies on exploitation by selecting the action with the highest Q-value for the current state, bypassing exploration.
* Return Values: Returns the updated Q-table and the reward from the final step of the episode, facilitating the evaluation of the learned policy.

_See [Reinforcement Learning Goes Deep (Part I): Q-learning Algorithm Implementation for a Grid World Environment](https://heseltime.github.io/rDai#rl-1) for more summary and analysis!_

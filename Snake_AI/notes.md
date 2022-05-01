# Reinforcement Learning
- Reinforcement learning (RL) is an area of machine learning concerned with how software agents ought to take actions in an environment in order to maximize the notion of cumulative reward
    - OR: RL is teching a software agent how to behave in an environment by telling   it how good it's doing

## Deep Q learning
- This approach extends reinforcement learning by using a deep neural network to predict the actions.

- Downfalls: Only practical for very small environments and quickly loses its feasibility when the number of states and actions in the environment increases

- Q Value = Quality of action

0. Init Q Value(= init model)
1. Choose action (model.predict(state), or random move)
2. Perform action
3. Measure reward
4. Update Q value (+ train model) [then repeat at step 1]

## Components
1. Agent(our computer player)
2. Environment(the game itself)
3. Reward(give agent an award to inform it on how well it is doing)
    - eat food: +10
    - game over: -10
    - else: 0

### Steps to follow
1. Agent    
    - game
    - model
    #### Training:
    - state = get_state(game)
    - action = get_move(state):
        - model.predict()
    - reward, game_over, score = game.play_step(action)
    - new_state = get_state(game)
    - remember
    - model.train()
2. Game
    - play_step(action)
        -> reward, game_over, score
3. Model (PyTorch)
    Linear_QNet(DQN)
    - model.predict(state)
        -> action

##### Action
- [1, 0, 0] -> Straight
- [0, 1, 0] -> Right turn
- [0, 0, 1] -> Left turn

- Using 3 numbers for our action we can never do a 180 degree turn(no backwards)

##### States (11 values)
[danger straight, danger right, danger left,

direction left, direction right,
direction up, direction down,

food left, food right,
food up, food down
]

##### Model
- Feed forward nueral net
    - Input layer(state)
    - Hidden layer
    - Output layer(3 outputs to predict the action)


##### Resources
- [Bellman Equations and Dyanmic Programming](https://login.cs.utexas.edu/sites/default/files/legacy_files/research/documents/6%20Bellman%20Eqs%20and%20DP.pdf )
- [Bellman Equation](https://www.geeksforgeeks.org/bellman-equation/ )
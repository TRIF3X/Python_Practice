# Reinforcement Learning
- Reinforcement learning (RL) is an area of machine learning concerned with how software agents ought to take actions in an environment in order to maximize the notion of cumulative reward
    - OR: RL is teching a software agent how to behave in an environment by telling   it how good it's doing

## Deep Q learning
- This approach extends reinforcement learning by using a deep neural network to predict the actions.

Downfalls: Only practical for very small environments and quickly loses its feasibility when the number of states and actions in the environment increases

## Components
1. Agent(our computer player)
2. Environment(the game itself)
3. Reward(give agent an award to inform it on how well it is doing)

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
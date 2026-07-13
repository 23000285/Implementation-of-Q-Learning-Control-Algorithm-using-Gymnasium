# Implementation-of-Q-Learning-Control-Algorithm-using-Gymnasium

## Aim

To implement the **Q-Learning control algorithm** using the Gymnasium `FrozenLake-v1` environment and learn an optimal action-value function that enables the agent to select suitable actions for reaching the goal state while avoiding holes.

---

## Problem Statement

The objective of this experiment is to train an agent in the Gymnasium `FrozenLake-v1` environment using the Q-Learning algorithm.

The agent must learn:

1. How to interact with the FrozenLake environment.
2. How to select actions using an epsilon-greedy strategy.
3. How to update the Q-table using the Q-Learning update rule.
4. How to derive the learned greedy policy from the Q-table.
5. How to evaluate the performance of the learned policy.

---

## Software Requirements

```bash
pip install gymnasium numpy matplotlib
```

---

## Environment Description

This experiment uses the Gymnasium `FrozenLake-v1` environment.

FrozenLake is a grid-world environment where the agent moves across frozen tiles and tries to reach the goal without falling into holes.

For the default 4 x 4 FrozenLake map:

| Component | Description |
|---|---|
| Environment | `FrozenLake-v1` |
| Map size | 4 x 4 |
| Observation space | 16 discrete states |
| Action space | 4 discrete actions |
| Actions | 0 = Left, 1 = Down, 2 = Right, 3 = Up |
| Reward | +1 for reaching the goal, 0 otherwise |
| Terminal states | Goal and hole states |

---

## Theory

Q-Learning estimates the optimal action-value function directly.

The action-value function $Q(s,a)$ represents the expected return obtained when the agent takes action $a$ in state $s$, and then follows the best possible policy afterward.

The Q-Learning update rule is:

$$
Q(S_t,A_t) \leftarrow Q(S_t,A_t) + \alpha
\left[
R_{t+1} + \gamma \max_{a} Q(S_{t+1},a) - Q(S_t,A_t)
\right]
$$

Where:

| Symbol | Meaning |
|---|---|
| $S_t$ | Current state |
| $A_t$ | Current action |
| $R_{t+1}$ | Reward received after taking action $A_t$ |
| $S_{t+1}$ | Next state |
| $\alpha$ | Learning rate |
| $\gamma$ | Discount factor |
| $Q(s,a)$ | Action-value function |
| $max_{a} Q(S_{t+1},a)$ | Maximum action value in the next state |

---

## Epsilon-Greedy Action Selection

During training, the agent uses epsilon-greedy action selection.

With probability $\epsilon$, the agent explores by selecting a random action.

With probability $1-\epsilon$, the agent exploits by selecting the action with the highest Q-value.

$$
a =
\begin{cases}
\text{random action}, & \text{with probability } \epsilon \\
\arg\max_{a} Q(s,a), & \text{with probability } 1-\epsilon
\end{cases}
$$

---

## Algorithm

1. Create the Gymnasium `FrozenLake-v1` environment.
2. Initialize the Q-table with zeros.
3. Set the learning rate $\alpha$, discount factor $\gamma$, and exploration rate $\epsilon$.
4. For each episode:
   - Reset the environment.
   - Select an action using epsilon-greedy action selection.
   - Execute the action.
   - Observe the reward and next state.
   - Update the Q-value using the Q-Learning update rule.
   - Move to the next state.
   - Stop when the episode terminates or truncates.
   - Reduce epsilon gradually.
5. After training, extract the learned greedy policy using the maximum Q-value action for each state.
6. Display the Q-table, state-value function, learned policy, and learning curve.

---

## Python Program

```python

# -------------------------------------------------
# Q-Learning Training
# -------------------------------------------------
# Write your code here







```
---

## Output

```text
Final Q-table:





Estimated State-Value Function:






Learned Policy:




Average reward over last 1000 episodes: 
```

---

## Result

```text



```

---

## Inference

```text



```

---


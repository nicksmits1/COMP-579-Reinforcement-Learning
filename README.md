# COMP-579-Reinforcement-Learning
Assignments and project completed as part of COMP 579 - Reinforcement Learning at McGill

Overview

These projects were developed as part of the COMP-579 course in 2025. They cover:
	•	Assignment 1: Implementation and analysis of bandit algorithms using Gaussian bandits, various learning rate strategies, ϵ-greedy approaches (with both constant and decaying ϵ), gradient bandit algorithms, and Thompson sampling. The experiments include visualizations of reward distributions, estimated action values, and performance metrics (instantaneous and cumulative regret) under both stationary and non-stationary conditions.
	•	Assignment 2: A deep dive into tabular reinforcement learning. This assignment compares SARSA and expected SARSA on the Frozen Lake environment using a softmax (Boltzmann) exploration strategy. It also includes a mathematical treatment of a simple three-state MDP where the Bellman equations are solved both analytically (using matrix inversion) and numerically (via iterative updates) to perform policy evaluation and derive the optimal policy.
	•	Assignment 3: Exploration of deep reinforcement learning techniques using neural network approximators. The value-based segment implements Q-learning and Expected SARSA on environments like Acrobot-v1 and ALE/Assault-ram-v5, incorporating experiments with different exploration (ϵ-greedy) strategies, learning rates, and the use of replay buffers. The policy-based segment covers REINFORCE and Actor-Critic methods, leveraging the policy gradient theorem with both fixed and decaying temperature parameters for Boltzmann policies.

⸻

Assignment 1: Bandit Algorithms
	•	Objective: Gain hands-on experience with bandit algorithms by simulating Gaussian bandits and experimenting with different update rules.
	•	Key Features:
	•	Simulation: Create a Gaussian bandit with multiple arms, sampling rewards based on a provided mean vector and fixed variance.
	•	Update Methods: Implement incremental averaging, fixed learning rate updates (with different α values), and a decaying learning rate update.
	•	Exploration Strategies: Code the ϵ-greedy algorithm (with both constant and decaying ϵ) and the gradient bandit algorithm.
	•	Advanced Techniques: Implement Thompson sampling and analyze performance under non-stationary conditions where bandit parameters change.
	•	Visualization: Plot reward trajectories, estimated vs. true values, and regret curves over multiple runs.

⸻

Assignment 2: Tabular RL and MDP Analysis
	•	Objective: Compare the performance of SARSA and expected SARSA on the Frozen Lake problem and analytically solve a simple MDP.
	•	Key Features:
	•	Tabular RL: Use a softmax (Boltzmann) exploration strategy to train agents on the Frozen Lake environment, experimenting with various temperature and learning rate settings. Performance is measured through multiple trials and visualized via training and testing reward graphs.
	•	Analytical Methods: Solve the Bellman equations for a three-state MDP:
	•	Policy Evaluation: Derive the value function for a given deterministic policy both analytically (using matrix inversion) and numerically (iterative updates).
	•	Optimal Policy: Solve the Bellman optimality equations to determine the optimal value function and policy.
	•	Visualization: Generate comparative plots that highlight the effect of hyperparameters on both training and testing performance.

⸻

Assignment 3: Deep Reinforcement Learning
	•	Objective: Implement and compare deep RL algorithms using neural network approximators in both value-based and policy-based frameworks.
	•	Key Features:
	•	Value-Based Methods:
	•	Algorithms: Implement Q-learning and Expected SARSA using multi-layer perceptron (MLP) models.
	•	Environments: Experiment on Acrobot-v1 and ALE/Assault-ram-v5.
	•	Techniques: Test different exploration (ϵ-greedy) strategies, learning rate schedules, and the use of replay buffers.
	•	Visualization: Plot training curves (mean and standard deviation) over multiple runs for various configurations.
	•	Policy-Based Methods:
	•	Algorithms: Implement REINFORCE and Actor-Critic methods using neural network approximations for both the policy and the state-value function.
	•	Approach: Leverage Boltzmann (softmax) policies, with experiments comparing fixed and decaying temperature settings.
	•	Visualization: Display performance curves comparing REINFORCE and Actor-Critic under multiple hyperparameter settings.
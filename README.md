# COMP-579-Reinforcement-Learning
Assignments and project completed as part of COMP 579 - Reinforcement Learning at McGill

<u>Assignment 1</u>: Implementation and analysis of bandit algorithms using Gaussian bandits, various learning rate strategies, ϵ-greedy approaches (with both constant and decaying ϵ), gradient bandit algorithms, and Thompson sampling. The experiments include visualizations of reward distributions, estimated action values, and performance metrics (instantaneous and cumulative regret) under both stationary and non-stationary conditions.

<u>Assignment 2</u>: A deep dive into tabular reinforcement learning. This assignment compares SARSA and expected SARSA on the Frozen Lake environment using a softmax (Boltzmann) exploration strategy. It also includes a mathematical treatment of a simple three-state MDP where the Bellman equations are solved both analytically (using matrix inversion) and numerically (via iterative updates) to perform policy evaluation and derive the optimal policy.

<u>Assignment 3</u>: Exploration of deep reinforcement learning techniques using neural network approximators. The value-based segment implements Q-learning and Expected SARSA on environments like Acrobot-v1 and ALE/Assault-ram-v5, incorporating experiments with different exploration (ϵ-greedy) strategies, learning rates, and the use of replay buffers. The policy-based segment covers REINFORCE and Actor-Critic methods, leveraging the policy gradient theorem with both fixed and decaying temperature parameters for Boltzmann policies.

⸻

<b>Assignment 1</b>: Bandit Algorithms

- Objective: Gain hands-on experience with bandit algorithms by simulating Gaussian bandits and experimenting with different update rules.
- Key Features:
	- Simulation: Create a Gaussian bandit with multiple arms, sampling rewards based on a provided mean vector and fixed variance.
	- Update Methods: Implement incremental averaging, fixed learning rate updates (with different α values), and a decaying learning rate update.
	- Exploration Strategies: Code the ϵ-greedy algorithm (with both constant and decaying ϵ) and the gradient bandit algorithm.
	- Advanced Techniques: Implement Thompson sampling and analyze performance under non-stationary conditions where bandit parameters change.
	- Visualization: Plot reward trajectories, estimated vs. true values, and regret curves over multiple runs.

⸻

<b>Assignment 2</b>: Tabular RL and MDP Analysis

- Objective: Compare the performance of SARSA and expected SARSA on the Frozen Lake problem and analytically solve a simple MDP.
- Key Features:
	- Tabular RL: Use a softmax (Boltzmann) exploration strategy to train agents on the Frozen Lake environment, experimenting with various temperature and learning rate settings. Performance is measured through multiple trials and visualized via training and testing reward graphs.
	- Analytical Methods: Solve the Bellman equations for a three-state MDP:
	- Policy Evaluation: Derive the value function for a given deterministic policy both analytically (using matrix inversion) and numerically (iterative updates).
	- Optimal Policy: Solve the Bellman optimality equations to determine the optimal value function and policy.
	- Visualization: Generate comparative plots that highlight the effect of hyperparameters on both training and testing performance.

⸻

<b>Assignment 3</b>: Deep Reinforcement Learning

- Objective: Implement and compare deep RL algorithms using neural network approximators in both value-based and policy-based frameworks.
- Key Features:
	- Value-Based Methods:
		- Algorithms: Implement Q-learning and Expected SARSA using multi-layer perceptron (MLP) models.
		- Environments: Experiment on Acrobot-v1 and ALE/Assault-ram-v5.
		- Techniques: Test different exploration (ϵ-greedy) strategies, learning rate schedules, and the use of replay buffers.
		- Visualization: Plot training curves (mean and standard deviation) over multiple runs for various configurations.
	- Policy-Based Methods:
		- Algorithms: Implement REINFORCE and Actor-Critic methods using neural network approximations for both the policy and the state-value function.
		- Approach: Leverage Boltzmann (softmax) policies, with experiments comparing fixed and decaying temperature settings.
		- Visualization: Display performance curves comparing REINFORCE and Actor-Critic under multiple hyperparameter settings.

⸻

<b>Final Project</b>: Evaluation of DQN Variants for ICU Sepsis Treatment

Objective: Investigate and compare multiple extensions of Deep Q-Networks (DQN) on the ICU-Sepsis-v2 environment, a clinically inspired benchmark simulating sepsis treatment in intensive care units. The goal was to determine whether architectural and algorithmic improvements could outperform the standard DQN baseline.
	•	Environment: ICU-Sepsis-v2 models sepsis treatment as a Markov Decision Process (MDP) with 716 discrete health states derived from real ICU patient data (MIMIC-III). The 25 discrete actions correspond to different combinations of intravenous fluid and vasopressor dosages. Rewards are sparse and outcome-based: +1 for patient survival, 0 otherwise.
	•	Algorithms Implemented:
	•	Base DQN – two-layer MLP, ε-greedy exploration, experience replay, target networks.
	•	Prioritized DQN – prioritizes transitions with large temporal-difference (TD) errors for improved sample efficiency.
	•	Double DQN – reduces overestimation bias by decoupling action selection from evaluation.
	•	Dueling DQN – separates value and advantage estimation for better state-action value decomposition.
	•	Multi-Step DQN – propagates multi-step returns for improved credit assignment.
	•	Noisy DQN – replaces ε-greedy with learned parameterized noise for adaptive exploration.
	•	Distributional DQN – predicts a full return distribution rather than just its expectation.
	•	Rainbow DQN – combines multi-step learning, distributional RL, prioritized replay, noisy nets, double Q-learning, and dueling architecture.
	•	Key Results:
	•	Best performance: Dueling DQN achieved the highest final returns (~0.8238), followed closely by Prioritized DQN (~0.8135).
	•	Base DQN and Double DQN performed similarly (~0.8089 and ~0.8056), while Rainbow, Multi-Step, and Distributional DQN underperformed, likely due to limited hyperparameter tuning.
	•	Prioritized DQN converged faster than Dueling DQN but to a slightly lower final return.
	•	Complex methods (Rainbow, Multi-Step) were more sensitive to small grid searches and environment vectorization quirks.
	•	Conclusion: Architectural improvements such as dueling networks and prioritized replay show promise for optimizing sepsis treatment policies in this simulated setting. More exhaustive hyperparameter searches may unlock the potential of more complex methods like Rainbow and Distributional DQN.

Note: This repo only contains the sections of the project I completed, thus methods mentioned in the project paper and outlined above are not included as they were completed by me team members, James Randolph and Abdullah Paracha.

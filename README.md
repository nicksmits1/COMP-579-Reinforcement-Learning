# COMP 579 — Reinforcement Learning

**Contributors:** Nicolas Smits, James Randolph (final project), Abdullah Paraha (final project)  
Projects completed for *COMP 579: Reinforcement Learning* (McGill University).  
This repository contains implementations and analyses spanning bandit algorithms, tabular RL, deep RL, and a final project on DQN variants for clinical decision-making.

---

## 🎰 A1 — Multi‑Armed Bandits  
**Topics:** Exploration–exploitation, regret minimization, non‑stationary environments  

This assignment introduced core bandit algorithms using simulated **Gaussian bandits**. The work compares learning rules, exploration strategies, and performance under both stationary and drifting reward distributions.

**Included methods:**
- Incremental updates & fixed learning‑rate updates  
- Decaying‑α updates for non‑stationary problems  
- **ϵ‑greedy** (constant & decaying ϵ)  
- **Gradient bandits**  
- **Thompson Sampling**  

**Outputs:**
- Reward trajectories  
- Estimated vs. true action values  
- Instantaneous and cumulative regret plots  

---

## 🧊 A2 — Tabular RL & MDP Analysis  
**Topics:** SARSA, Expected SARSA, policy evaluation, small MDPs  

This assignment explored tabular reinforcement learning on **FrozenLake-v1**, studied softmax (Boltzmann) exploration, and analyzed a simple three‑state MDP both analytically and numerically.

**Key components:**
- SARSA vs. Expected SARSA with Boltzmann policies  
- Hyperparameter sweeps (temperature, learning rate)  
- Train/test reward curves  
- Closed‑form solution of Bellman equations  
- Numerical policy evaluation via iterative updates  
- Derivation of the optimal policy

Training results: Tabular SARSA and Expected SARSA final training score vs learning rate and temperature.

<img width="772" height="498" alt="Screenshot 2025-12-06 at 12 25 25" src="https://github.com/user-attachments/assets/352608e1-94ef-4448-a0d0-b897ec074a0d" />
<img width="768" height="497" alt="Screenshot 2025-12-06 at 12 25 40" src="https://github.com/user-attachments/assets/edeecc8a-ba44-41e0-9d42-ca5337cc27d3" />
<img width="767" height="497" alt="Screenshot 2025-12-06 at 12 25 51" src="https://github.com/user-attachments/assets/22095bc2-5190-4019-a52c-928203587491" />
<img width="768" height="497" alt="Screenshot 2025-12-06 at 12 26 02" src="https://github.com/user-attachments/assets/33372d77-f819-4d7c-82b3-7b618c12ade1" />


Training results: Tabular SARSA and Expected SARSA rewards over training episodes.

<img width="769" height="340" alt="Screenshot 2025-12-06 at 12 27 48" src="https://github.com/user-attachments/assets/0149e1f0-3233-4f31-acc0-5e26376ac528" />
<img width="769" height="341" alt="Screenshot 2025-12-06 at 12 28 00" src="https://github.com/user-attachments/assets/02199b9f-338b-4729-b940-8b572d01a4a9" />


Testing results: Tabular SARSA and Expected SARSA rewards over testing episodes.

<img width="769" height="341" alt="Screenshot 2025-12-06 at 12 28 13" src="https://github.com/user-attachments/assets/903e1bf8-0ba4-41a4-bfcd-3338a0011323" />
<img width="768" height="341" alt="Screenshot 2025-12-06 at 12 28 28" src="https://github.com/user-attachments/assets/7fe1a555-1c75-42b4-ae88-7d97435afaaa" />


---

## 🔥 A3 — Deep Reinforcement Learning  
**Topics:** Value‑based & policy‑based deep RL  

This assignment implemented neural approximators for both Q‑learning and policy gradients using environments such as **Acrobot‑v1** and **ALE/Assault‑ram‑v5**.

### Value‑Based Methods
- Q‑learning with MLP approximators  
- Expected SARSA with function approximation  
- Replay buffers  
- Exploration strategies (ϵ‑greedy, decays)  

### Policy‑Based Methods
- **REINFORCE**  
- **Actor–Critic** (separate policy & value networks)  
- Experiments with Boltzmann exploration (fixed & decaying temperature)  

### Outputs
- Training curves (mean ± std) across seeds  
- Comparisons of stability and convergence across architectures  

### Results

Training curves for the Deep Q-Learning (with replay buffer) and Expected SARSA (with replay buffer) models on the Acrobot-v1 and ALE-Assault-Ram-v5 gymnasium environments for various learning rates, \alpha and exploration rates, \epsilon.

<img width="758" height="523" alt="Screenshot 2025-12-06 at 00 33 29" src="https://github.com/user-attachments/assets/560c2b10-9972-4ea6-9bfe-05ff657be867" />

<img width="758" height="520" alt="Screenshot 2025-12-06 at 00 33 44" src="https://github.com/user-attachments/assets/cae1d6c0-b050-4e4f-a127-d875a97d8c0c" />


Training curves for the REINFORCE and Actor-Critic models on the Acrobot-v1 and ALE-Assault-Ram-v5 gymnasium environments for a fixed and decaying temperature.

<img width="759" height="940" alt="Screenshot 2025-12-06 at 00 21 36" src="https://github.com/user-attachments/assets/1cf2c133-2214-4d1a-ac5b-bb9ca37a4d2b" />

---

## 🏥 Final Project — DQN Variants for ICU Sepsis Treatment  
**Environment:** **ICU‑Sepsis‑v2** — a clinically inspired RL benchmark built from MIMIC‑III data.

This project evaluated whether modern DQN extensions outperform the baseline DQN on sepsis‑treatment decision‑making. The MDP includes **716 health states** and **25 discrete treatment actions** involving fluid and vasopressor dosing.

### Algorithms Implemented (only those completed by Nicolas Smits)
- **Base DQN** (MLP + replay + target networks)  
- **Prioritized DQN** (TD‑error‑based sampling)  
- **Double DQN** (reduced overestimation bias)  
- **Dueling DQN** (value + advantage streams)  

*(Methods such as Rainbow, Distributional DQN, Noisy DQN, and Multi‑Step DQN were executed by teammates and are referenced for completeness but not included in this repo.)*

### Key Findings
- **Dueling DQN** achieved the strongest final return (~0.8238).  
- **Prioritized DQN** converged faster but plateaued slightly lower (~0.8135).  
- Baselines (standard DQN, Double DQN) reached ~0.8089–0.8056.  
- More complex methods (e.g., Rainbow) were highly sensitive to limited hyperparameter searches.  

**Conclusion:**  
Architectural improvements like dueling architectures and prioritized replay show meaningful benefits for clinical decision‑making in this simulated ICU setting. Deeper hyperparameter tuning may unlock stronger performance for more complex variants.

Survival rate and episode length results over training episodes.

<img width="1005" height="322" alt="Screenshot 2025-12-06 at 12 30 46" src="https://github.com/user-attachments/assets/c0660ece-ffdc-4f40-acd7-d474250efbf5" />


---

## 📂 Repository Structure

```
COMP-579-Reinforcement-Learning/
│
├── Assignment1/
│   └── ... bandit algorithms & analysis
├── Assignment2/
│   └── ... tabular RL & MDP work
├── Assignment3/
│   └── ... deep RL implementations (value & policy based)
├── Final_Project/
│   └── ... DQN variants for ICU-Sepsis-v2
└── README.md
```

---

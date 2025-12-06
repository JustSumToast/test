# Group 4: Probabilistic Treasure Hunt README

**Authors:** Cole Buckingham, Regan Lai, Victor NG

This GUI application generates a 20x20 Treasure Hunt grid with static walls, multiple treasures, and traps.
The user can visualize an agent using **Bayesian inference** to detect treasures under sensor uncertainty and select actions based on the belief distribution.

---

## Instructions on How to Run the Code

1. Install Python 3.x and a compatible IDE (e.g., VS Code, PyCharm, or run from terminal).
2. Download the source code files.
3. Run the main Python file (`GUI Assignment 4 Version [Group 3]`) to launch the GUI.
4. Use **Generate Grid** to create a new game map.
5. Set sensor noise parameters (false positive/false negative rates).
6. Click **Start Human/AI vs AI** to run the agent and visualize treasure detection and movement.

---

## Screenshot of Code
<img width="1189" height="1054" alt="image" src="https://github.com/user-attachments/assets/05f2ea13-9e7d-4652-bc3e-95a693d9d1c7" />

---

## Sensor Model and Bayesian Update

<img width="585" height="165" alt="image" src="https://github.com/user-attachments/assets/16e803f0-cb3e-4a78-9526-1057692ff168" />

This update occurs for each scan around the agent's location, incorporating noisy observations.

---

## Belief Representation

* Belief is stored as a **2D array** of size equal to the grid (e.g., 20x20).
* Each cell contains the probability of a treasure being present.
* Beliefs are initialized uniformly across all non-wall cells and updated after each scan.

---

## Decision Policy

* At each turn, the agent:

  1. Scans nearby cells to update the belief distribution.
  2. Chooses the move that maximizes expected utility: moves towards cells with high belief of containing a treasure.
  3. Avoids traps and oscillatory moves.

---

## Experiments

* **Grid Configurations:** Randomly generated 20x20 grids with 2-4 treasures, 2-3 traps, and static walls.
* **Noise Levels:**

  * Low: FP=0.05, FN=0.05
  * Medium: FP=0.1, FN=0.2
  * High: FP=0.2, FN=0.3
* **Reproducibility:** Run each experiment with 10 different random seeds for averaging metrics.

---

## Example Results

| Noise Level  | Avg Steps to Detect Treasure | Avg Number of Scans | Avg Entropy at Detection | Detection Accuracy |
| ------------ | ---------------------------- | ------------------- | ------------------------ | ------------------ |
| Low Noise    | 14.2                         | 6.1                 | 0.41                     | 100%               |
| Medium Noise | 21.8                         | 9.7                 | 0.63                     | 90%                |
| High Noise   | 32.4                         | 15.2                | 0.89                     | 70%                |

### Example Belief Heatmaps

**Belief at t=0 (uniform across all cells)**

**Belief after k scans:**

```
0.004 0.006 0.009 0.013 0.021 0.034 0.042 0.051 0.060 0.055
0.004 0.007 0.010 0.015 0.024 0.038 0.050 0.066 0.078 0.071
0.003 0.005 0.009 0.013 0.021 0.040 0.065 0.090 0.112 0.101
0.002 0.004 0.007 0.011 0.018 0.033 0.052 0.079 0.130 0.142
0.002 0.003 0.006 0.009 0.014 0.026 0.042 0.068 0.121 0.168   <--- belief peak forming
```

**Belief at Detection:**

```
0.001 0.002 0.003 0.005 0.008 0.012 0.018 0.027 0.035 0.028
0.001 0.002 0.003 0.006 0.009 0.014 0.022 0.034 0.048 0.036
0.001 0.002 0.004 0.007 0.011 0.019 0.032 0.051 0.073 0.054
0.001 0.002 0.004 0.008 0.014 0.025 0.043 0.072 0.123 0.109   <--- center
0.001 0.002 0.003 0.006 0.011 0.021 0.039 0.068 0.147 0.192   <--- treasure
```

*Entropy can be computed at each scan step to analyze convergence.*

---

## Use of Generative AI

We used **ChatGPT** to:

* Assist in formatting and structuring this README.
* Suggest visualization and reporting methods.

All **core algorithmic code**, **Bayesian inference implementation**, **grid generation**, **multi-treasure handling**, and **GUI code** were written and tested by the team (Cole Buckingham, [Your Team Members]). AI assistance was limited to **documentation structure** and **explanations**, not the original code development.

# Group 3: Treasure Hunt Adversarial Search README

**Authors:** Regan Lai, Victor NG, Cole Buckingham

This GUI application generates a 15x15 Treasure Hunt grid with static walls, multiple treasures, and traps.  
The user can visualize **Minimax** and **Alpha-Beta Pruning** algorithms in a turn-based competitive setting, where two agents compete to collect treasures while avoiding traps.

---

## Instructions on How to Run the Code

1. Install Python 3.x and a compatible IDE (e.g., VS Code, PyCharm, or run from terminal).  
2. Download the source code files.  
3. Run the main Python file (`GUI Assignment 3 Version [Group 3].py`) to launch the GUI.  
4. Use **Generate Grid** to create a new game map.  
5. Choose either **Human vs AI** or **AI vs AI**.  
6. Select the AI algorithm for Agent B from the dropdown (options: BFS, DFS, UCS, A*, Greedy, Minimax, Alpha-Beta).  
7. Set the search depth (relevant for Minimax/Alpha-Beta).  
8. Click **Start** to play or watch the simulation.  

---

## Evaluation Function

The evaluation function determines the desirability of a state for **Agent A**:

* **Traps:** Hitting a trap is heavily penalized (-1000), while the opponent hitting a trap gives a positive score (+1000).  
* **Treasures:** Rewards collecting treasures.  
  * Score increases for treasures already collected.  
  * Score decreases with Manhattan distance to remaining treasures (closer treasures are better).  
  * Slight bonus for proximity to all remaining treasures.  
* **Oscillation Penalty:** Penalizes staying in the same location repeatedly to prevent agents from moving back and forth indefinitely.  

This heuristic encourages agents to efficiently collect treasures while avoiding traps and repetitive moves.

---

## Comparison of Minimax and Alpha-Beta Pruning

We tested the AI on multiple depth levels and recorded the **nodes expanded** and **execution time**.

| Algorithm      | Depth | Nodes Expanded | Execution Time (s) | Outcome                       |
| -------------- | ----- | -------------- | ----------------- | ----------------------------- |
| Minimax        | 2     | 310            | 0.25              | Win                           |
| Alpha-Beta     | 2     | 180            | 0.19              | Win                           |
| Minimax        | 3     | 650            | 0.62              | Loss                          |
| Alpha-Beta     | 3     | 320            | 0.35              | Win                           |
| Alpha-Beta     | 4     | 720            | 0.75              | Win                           |

**Observations:**

* Alpha-Beta Pruning significantly reduces nodes expanded compared to Minimax while producing the same or better outcomes.  
* Higher depth increases planning accuracy but also execution time.  
* Oscillation detection ensures that agents stuck in loops will instead move toward the nearest treasure efficiently.  

---

## Screenshot

Sample visualization of **Alpha-Beta Pruning** agent moving toward treasures:

<img width="1134" height="784" alt="Assignment #3 Pic" src="https://github.com/user-attachments/assets/a0938c1d-de55-4013-8594-9dfe4626f84d" />

---

## Use of Generative AI

We used **ChatGPT** to:

* Assist in formatting and structuring this README.  
* Clarify evaluation function design and oscillation handling.  
* Suggest comparisons between Minimax and Alpha-Beta in documentation.  

All **algorithm implementation**, **grid generation**, **multi-treasure handling**, **oscillation detection**, and **GUI code** were written and tested by the team (Regan Lai, Victor NG, and Cole Buckingham). AI assistance was limited to **documentation structure** and **explanations**, not the original code development.

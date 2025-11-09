# Group 3: Treasure Hunt Grid Heuristic Search README

**Authors:** Regan Lai, Victor NG, Cole Buckingham

This GUI application generates a 20x20 Treasure Hunt grid with static walls, multiple treasures, and traps.
The user can visualize **A*** and **Greedy Best-First Search (GBFS)** algorithms as they search for treasures while avoiding traps and walls.

---

## Instructions on How to Run the Code

1. Install Python 3.x and a compatible IDE (e.g., VS Code).
2. Download the source code files.
3. Run the main Python file to launch the GUI.
4. In the GUI, select either **A*** or **Greedy** as the search algorithm.
5. Click **Run Search** to visualize how the algorithm explores the grid and finds treasures.

---

## Heuristic Design and Implementation

* **Heuristic Function:** Manhattan distance is used to estimate the cost from any cell to the nearest treasure.
* **A* Implementation:** Combines the actual path cost `g(n)` and heuristic `h(n)` to calculate `f(n) = g(n) + h(n)` for node expansion.
* **Greedy Implementation:** Uses the heuristic value `h(n)` only, prioritizing nodes estimated to be closer to a treasure without considering path cost.
* **Multi-Treasure Handling:** Both algorithms iteratively select the nearest remaining treasure and expand the path accordingly, updating the path and heuristic values at each stage.
* **Grid Representation:** A 20x20 2D grid with states for empty cells, walls, traps, and treasures.

---

## Comparison of A* and Greedy Performance

| Algorithm  | Test Map | Path Cost | Nodes Expanded | Runtime (seconds) |
| ---------- | -------- | --------- | -------------- | ----------------- |
| **A***     | Map 1    | 18        | 104            | 0.10              |
| **Greedy** | Map 1    | 19        | 110            | 0.07              |
| **A***     | Map 2    | 20        | 122            | 0.12              |
| **Greedy** | Map 2    | 22        | 130            | 0.08              |
| **A***     | Map 3    | 17        | 99             | 0.09              |
| **Greedy** | Map 3    | 19        | 105            | 0.06              |

> *Note: Values are sample results; actual performance may vary based on grid configuration.*

---

## Screenshot

Sample visualization of **A*** algorithm finding the treasure path (highlighted in blue):

<img width="700" height="580" alt="image" src="https://github.com/user-attachments/assets/91a16a65-7143-4259-bad6-b4a1e22feadd" />

---

## Use of Generative AI

We used **ChatGPT** to:

* Assist in formatting and structuring this README.
* Clarify heuristic implementation details and compare A* vs Greedy algorithms.
* Provide guidance on documenting test results clearly.

All **algorithm logic**, **grid generation**, **multi-treasure handling**, and **GUI implementation** were written and tested by the team (Regan Lai, Victor Ng, and Cole Buckingham). AI assistance was limited to **documentation structure**, **clarification**, and **explanations**, not the original code development.

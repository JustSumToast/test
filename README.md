# Group 3: Treasure Hunt Grid With Static Walls

**Authors:** Regan Lai, Victor NG, Cole Buckingham  

This GUI application generates a 10x10 Treasure Hunt grid with static walls at fixed positions.  
The user can visualize **Breadth-First Search (BFS)**, **Depth-First Search (DFS)**, and **Uniform Cost Search (UCS)** algorithms as they search for the treasure while avoiding traps and walls.

---

## 🧩 Instructions on How to Run the Code

1. Download Visual Code Studio or any program able to run Python.
2. Download Source Code.
3. Run the program.
4. When the GUI launches, select the desired search algorithm (BFS, DFS, or UCS) from the options.
5. Click **Start Search** to visualize how the algorithm explores the grid and locates the treasure.

---

## ⚙️ Description of Implementation

### Data Structures
- **Grid:** Implemented as a 2D list (10x10) where each cell contains a state (empty, wall, trap, or treasure).
- **Node Representation:** Each node includes `(x, y)` coordinates, a reference to its parent node, and the cost to reach it.
- **Frontier Structures:**
  - **BFS:** Uses a `queue.Queue` to ensure nodes are explored in order of discovery.
  - **DFS:** Uses a `list` as a stack (LIFO) for deep exploration.
  - **UCS:** Uses a `heapq` priority queue to always expand the node with the lowest path cost.

### Design Decisions
- Each search algorithm is modularized, allowing easy switching between BFS, DFS, and UCS.
- The environment’s walls and traps are static, ensuring consistent comparisons between algorithms.
- The GUI highlights explored nodes and displays the final path to the treasure.
- UCS accounts for path cost, while BFS and DFS assume uniform step costs.

---

## 📊 Comparison of BFS, DFS, and UCS Results

| Algorithm | Path Cost | Nodes Expanded | Runtime (seconds) |
|------------|------------|----------------|-------------------|
| **BFS**    | 12         | 86             | 0.04              |
| **DFS**    | 18         | 102            | 0.03              |
| **UCS**    | 12         | 65             | 0.05              |

> *Note: Results are sample values based on our test grid; actual performance may vary.*

---

## 🖼️ Screenshot

Below is a sample visualization of the DFS algorithm finding the treasure path (highlighted in blue):

<img width="440" height="521" alt="DFS Screenshot" src="https://github.com/user-attachments/assets/98b22480-66c5-42b2-83d1-3e386f280679" />

## 🤖 Use of Generative AI

We used **ChatGPT** to:
- Help structure and format this README file.
- Clarify differences between BFS, DFS, and UCS during documentation.
- Suggest minor debugging tips for DFS recursion and UCS path tracking.

All **algorithm logic**, **grid generation**, and **GUI implementation** were written and tested by the team (Regan Lai, Victor Ng, and Cole Buckingham).  
AI assistance was limited to **documentation improvements** and **clarifications**, not core code development.

---

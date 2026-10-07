# 8-Puzzle Solver — BFS & DFS

A Python-based **8-Puzzle Solver** that solves the classic 3×3 sliding-tile puzzle using two uninformed search algorithms:

* **Breadth-First Search (BFS)**
* **Depth-First Search (DFS)**

The project compares both algorithms based on **solution path length, nodes expanded, and execution time**.

## 📌 Project Overview

The 8-Puzzle consists of a 3×3 board containing eight numbered tiles and one blank space.

The solver takes a starting state and searches for a predefined goal state by moving the blank tile:

* Up
* Down
* Left
* Right

Each move has a unit cost.

BFS and DFS use the same puzzle model and goal state, allowing their performance to be compared fairly.

## 🎯 Objectives

The main objectives of this project are:

1. Implement BFS for solving the 8-Puzzle.
2. Implement DFS for solving the 8-Puzzle.
3. Compare BFS and DFS performance.
4. Count the number of nodes expanded.
5. Measure execution time.
6. Compare solution path lengths.
7. Visualize the results using charts.

## 🏗️ System Architecture

The project follows the **C4 architectural model**.

### Level 1 — Context

The main user is the student/user who:

1. Selects an 8-Puzzle test case.
2. Runs the solver.
3. Receives the solution path and performance results.

The system uses the Python runtime and libraries such as `time`, `cProfile`, and `matplotlib`. No database or network service is required.

### Level 2 — Containers

The system is divided into the following major containers:

| Container       | Responsibility                                 |
| --------------- | ---------------------------------------------- |
| Input Module    | Stores and provides the test cases             |
| Puzzle Model    | Represents the board and generates legal moves |
| Search Engine   | Executes BFS or DFS                            |
| Visited Set     | Stores explored states                         |
| Profiler Module | Measures execution time and nodes expanded     |
| Output & Report | Displays results and generates charts          |

### Level 3 — Components

The **Search Engine** contains:

* **Frontier** — queue for BFS and stack for DFS
* **Goal Test** — checks whether the current state is the goal
* **Successor Generator** — generates possible next states
* **Explored Set** — prevents repeated state expansion
* **Node Counter** — counts expanded nodes
* **Path Reconstructor** — reconstructs the solution path

The main structural difference between BFS and DFS is the data structure used by the Frontier: **queue for BFS and stack for DFS**.

## 🧩 Main Components

### `Node`

Stores:

* Current puzzle state
* Parent node
* Move performed
* Depth

### `get_neighbors(state)`

Generates all legal states by moving the blank tile up, down, left, or right.

### `is_goal(state)`

Checks whether the current puzzle state matches the goal state.

### `bfs(start, goal)`

Uses a **queue-based search** to find the shortest solution path.

### `dfs(start, goal)`

Uses a **stack-based search** to explore the puzzle states.

### `reconstruct_path(node)`

Follows parent links from the goal node back to the starting node to construct the final solution path.

### `run_profile(algo, start, goal, runs=7)`

Measures algorithm execution time using `time.perf_counter()` and averages the results over seven runs.

### `plot_results(results)`

Creates bar charts for comparing execution time and nodes expanded.

## 🔍 BFS vs DFS

| Feature         | BFS                      | DFS                        |
| --------------- | ------------------------ | -------------------------- |
| Data Structure  | Queue                    | Stack                      |
| Search Type     | Breadth-first            | Depth-first                |
| Shortest Path   | Yes, for unit-cost moves | Not guaranteed             |
| Memory Usage    | Generally higher         | Generally lower            |
| Search Strategy | Explores level by level  | Explores one branch deeply |
| Implementation  | Queue-based              | Stack-based                |

The project uses the same puzzle rules and goal state for both algorithms so that the comparison remains fair.

## 📊 Performance Evaluation

The solver evaluates three test cases:

* **Easy**
* **Medium**
* **Hard**

For each test case, BFS and DFS are evaluated using:

* Execution time
* Nodes expanded
* Solution path length

The profiler averages **7 runs per algorithm for each test case** to obtain the timing results.

## 🛠️ Technologies Used

* **Python**
* Breadth-First Search (BFS)
* Depth-First Search (DFS)
* `time`
* `cProfile`
* `matplotlib`

## 📁 Suggested Project Structure

```text
8-puzzle-solver/
│
├── README.md
├── main.py
├── solver.py
├── profiler.py
├── results/
│   ├── results.csv
│   └── charts/
│
└── screenshots/
```

> Adjust the filenames above if your actual Python files use different names.

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone https://github.com/sanchitmagdum17/8-puzzle-solver.git
```

### 2. Open the project directory

```bash
cd 8-puzzle-solver
```

### 3. Install required library

```bash
pip install matplotlib
```

### 4. Run the program

```bash
python main.py
```

The program will execute the selected test cases and generate the solution and performance results.

## 📈 Output

The solver produces:

* Solution path
* Number of nodes expanded
* Execution time
* BFS vs DFS comparison
* Performance charts

## 💡 Design Decisions

The **Puzzle Model** is separated from the **Search Engine**, allowing BFS and DFS to use the same movement rules.

The Frontier is the main structural difference between the two algorithms:

```text
BFS → Queue
DFS → Stack
```

Profiling is kept separate from the search logic so that performance-measurement code does not interfere with the actual algorithms.

## 🤖 AI Contribution

AI tools were used during development for:

* Suggesting the C4 diagram layout
* Drafting architecture explanations
* Formatting the report

The 8-Puzzle BFS/DFS system was selected from the SLE-2 work, and the architecture was reviewed against the implementation.

## 🎓 Academic Information

**Course:** 02AML204 — Introduction to Artificial Intelligence
**SLE:** SLE-3 — Architectural Design (Full C4 Model)
**Student:** Sanchit Sachin Magdum
**PRN:** 25UAM133
**Division:** B
**Department:** CSE (AI & ML)

## 📝 Conclusion

This project demonstrates how the same 8-Puzzle problem can be solved using different uninformed search strategies.

The C4 architecture separates the system into understandable levels and responsibilities, while the BFS and DFS implementations demonstrate how the choice of data structure affects search behavior and performance.

The project shows that **BFS guarantees the shortest path for this unit-cost puzzle, while DFS does not guarantee the shortest path**.

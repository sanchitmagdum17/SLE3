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
2. Runs the solv

Student: Assylay Askarkyzy
Course: Algorithms and Data Structures

Overview

This project implements a complete graph toolkit with BFS and DFS algorithms as per Assignment 4 requirements. The implementation includes a Graph ADT, BFS with shortest-path finding, DFS (both recursive and iterative), cycle detection, and a maze solver application.

Project Structure
ADS-Assignment4-Graph-BFS-DFS/
├── src/
│   ├── graph/         # Graph ADT and implementations
│   ├── bfs/           # BFS algorithms and shortest path
│   ├── dfs/           # DFS algorithms and cycle detection
│   ├── applications/  # Part D: Maze solver application
│   └── io/            # Input/Output handlers
├── test/              # Test cases (25+ individual tests)
├── data/              # Sample input files
├── scripts/           # Build and run scripts
├── report/            # Assignment report (PDF)
└── docs/              # Documentation and sample outputs
How to Run
Prerequisites

Java JDK 8 or higher

(Optional) JUnit 5 for running tests

Compilation
# Make script executable
chmod +x scripts/compile.sh

# Compile the project
./scripts/compile.sh
Running the Program
# Make script executable
chmod +x scripts/run.sh

# Option 1: Run Main example (default)
./scripts/run.sh

# Option 2: Run Maze Solver (Part D)
./scripts/run.sh 2

# Option 3: Run tests (requires JUnit)
./scripts/run.sh 3
Running Individual Classes
# Compile first (if not already compiled)
./scripts/compile.sh

# Run Main class
java -cp build Main

# Run Maze Solver
java -cp build applications.MazeSolver

# Run specific test (example)
java -cp build:lib/junit.jar org.junit.runner.JUnitCore GraphTest
Neighbor Ordering

For deterministic output as required by the assignment, neighbors are ordered using:

Natural ordering if vertices implement Comparable (e.g., Integer, String)

String comparison for string vertices

Hash-code ordering as a fallback for custom objects

This ensures BFS and DFS produce consistent, reproducible traversal orders.

Input Formats Supported
1. Edge List Format
   n m directed(0/1) weighted(0/1)
u1 v1 [w1]
u2 v2 [w2]
...
n – number of vertices

m – number of edges

directed – 0 for undirected, 1 for directed

weighted – 0 for unweighted, 1 for weighted

Vertices can be integers (0…n-1) or strings.
Example file: data/sample_edgelist.txt

2. Maze/Grid Format (Part D)
   rows cols
row1_char1 row1_char2 ...
row2_char1 row2_char2 ...
...
S – start position

T – target position

# – wall (impassable)

. – free cell (passable)

Example file: data/maze_input.txt
Test Cases Included

The test suite includes 25+ individual tests covering:

Empty graph

Single isolated vertex

Disconnected graphs

Multiple connected components

Cycle detection (directed and undirected)

BFS shortest-path correctness

Deterministic DFS traversal order

Invalid input handling

Stress testing with large graphs (1000+ vertices)

Part D: Maze Solver Application
The maze solver implements the chosen application from Part D:

Input: N × M grid with walls (#) and free cells (.)

Algorithm: BFS for shortest path in an unweighted grid

Output:

Shortest path length

Path coordinates

Visual grid representation with path marked as *


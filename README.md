# 15 Puzzle Solver

## 📌 Project Description

This project implements a 15-puzzle solver using the Iterative Deepening A* (IDA*) algorithm with the Manhattan Distance heuristic. It validates solvable, computes optimal move sequences, and supports step-by-step output for multiple test cases.

The Java-based application solves the classic **15-puzzle** using two search algorithms:

- **Iterative Deepening A\*** (IDA\*)
- **A\*** Search (MinHeap-based)

Both implementations use the **Manhattan Distance heuristic** to evaluate move priorities. The program supports multiple test cases, includes a validity check for each puzzle, and prints execution time, solution steps, and goal validation.

---

## 🛠 How to Compile and Run

### Requirements
- Java Development Kit (JDK) 8 or above

### Compilation
Make sure all `.java` files are in the same folder, then run:

```bash
javac *.java
```

### Running the Main Program
To test both A\* and IDA\* solvers with sample puzzles:

```bash
java PerformanceTests
```

To run the individual solver:

```bash
java RMIT_15_Puzzle_Solver
```

### Running Unit Tests

```bash
java UnitTests
```

> You may also run unit tests via an IDE like IntelliJ IDEA or Eclipse with JUnit 5.

---

## ✅ Expected Output

Each test case prints:
- Initial puzzle state
- Execution time (nanoseconds)
- Move sequence to reach the goal (e.g., `"LLDRU"`)
- Goal verification status (`true` or `false`)

---

## 🧠 Algorithms Used

### 🔹 Iterative Deepening A\*
- Uses depth-limited DFS and iteratively increases the bound based on `f(n) = g(n) + h(n)`
- Guarantees optimal solution with limited memory footprint
- Recursive backtracking logic in `IDAStar.java`

### 🔹 A\* Search
- Uses a **MinHeap** (priority queue) for efficient node selection
- Tracks visited states via a custom **HashSet**
- Designed to return optimal path using `f(n) = g(n) + h(n)`

---

## 📂 Project Structure

| File                   | Purpose |
|------------------------|---------|
| `Puzzle_Solver.java`   | Main class that runs IDA\* solver |
| `AStar.java`           | A\* search implementation |
| `IDAStar.java`         | IDA\* solver logic |
| `Node.java`            | Puzzle state representation |
| `Helper.java`          | Utility functions: validation, goal checks, Manhattan heuristic |
| `MinHeap.java`         | Priority queue for A\* |
| `HashSet.java`         | Custom hash set for duplicate state detection |
| `SolvablePuzzle.java`  | Set of predefined test cases |
| `PerformanceTests.java`| Benchmarking tool for comparing A\* vs IDA\* |
| `UnitTests.java`       | JUnit tests for helper and core functions |

---

## 🔍 Notes

- Blank tile is represented by `0`.
- Supports only **4x4** boards (15-puzzle).
- Solvability is determined by inversion parity and blank row position.
- Unit tests ensure correctness of goal detection, solvability, heuristics, and core functionality.


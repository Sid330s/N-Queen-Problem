# N-Queen Problem Using Hill Climbing Algorithm

## **Project Overview**

This project solves the **N-Queen Problem** using the **Hill Climbing Algorithm** in Python. The N-Queen problem involves placing N queens on an N×N chessboard such that no two queens threaten each other. A queen can attack another if they are placed on the same row, column, or diagonal.

The **Hill Climbing Algorithm** is a local search optimization technique that iteratively moves towards the solution by selecting the best neighboring state (i.e., the state with the fewest conflicts).

---

## **Project Details**

### **Title:**  
N-Queen Problem using Hill Climbing Algorithm

### **Type:**  
Course Project - Artificial Intelligence

### **Group No:**  
TY-58

### **Guide:**  
Prof. (Dr.) Bhutkar Ganesh Dattatray

### **Members:**
1. **Prashil Jambhulkar** (Roll No: 11810849)
2. **Sampatlal Jangid** (Roll No: 11811238)
3. **Siddharth Kale** (Roll No: 11810562)
4. **Vedant Mahajan** (Roll No: 11810123)

---

## **Objective**

The primary objective of this project is to implement the **Hill Climbing Algorithm** to solve the **N-Queen Problem**. The project involves:
1. Initializing a random board configuration.
2. Calculating the number of attacks (conflicts) between queens.
3. Iteratively adjusting the position of queens to reduce the number of conflicts.
4. Stopping when a solution is found (i.e., zero conflicts) or when the algorithm reaches a local optimum.

---

## **How It Works**

1. **Initialization:**
   - The board is initialized randomly, placing one queen in each row. Each queen is randomly placed in one of the available columns.
   
2. **Hill Climbing Algorithm:**
   - The algorithm starts by calculating the number of attacking queens (conflicts) for the current configuration.
   - It then iteratively selects a neighboring configuration where the number of conflicts is minimized. A neighboring configuration is generated by moving one queen to another position in its column.
   - If the new configuration has fewer conflicts than the previous configuration, it is selected as the next state.
   - If the number of conflicts remains the same after several moves, the algorithm attempts a new random board configuration to avoid getting stuck in a local minimum.

3. **Stopping Criteria:**
   - The algorithm stops when a solution with zero conflicts is found.
   - If the algorithm cannot improve after a set number of iterations (Maximum Still Hn), a new random board configuration is tried.

![states](https://github.com/Sid330s/N-Queen-Problem/blob/main/docs/states.jpeg)

---

## **Code Explanation**

### **Class: AIProject**
- **Attributes:**
  - `nQueens`: The number of queens (input by the user).
  - `board`: A list representing the current positions of queens on the board.
  - `lastHn`: The current heuristic (number of conflicts).
  - `noOffStillHn`: A counter for the number of iterations with no improvement.
  
- **Methods:**
  - `initBoard()`: Initializes the board with a random configuration of queens.
  - `printBoard(board)`: Prints the current board configuration with queens represented as "Q" and empty cells as ".".
  - `noOffAttacks(board)`: Calculates the number of conflicts (attacks) on the board.
  - `findHn(move)`: Calculates the heuristic (number of attacks) after making a potential move.
  - `makeNextMove()`: Chooses the best next move to minimize conflicts, using the Hill Climbing strategy.
  - `solve()`: The main method that runs the Hill Climbing algorithm until a solution is found.

### **Input:**
- The user is prompted to input the number of queens (`n`).

### **Output:**
- The board is printed at the initial state, showing the randomly placed queens.
- The board is printed again after the Hill Climbing algorithm finds a solution (zero conflicts).

---

## **Example Execution**

```
Enter the Number of Queens : 4
Init Board
[2, 0, 3, 1]
Q . . .
. . . Q
. Q . .
. . Q .
Solution Board
. . Q .
Q . . .
. . . Q
. Q . .
```

### **Explanation:**
1. **Init Board** shows the randomly initialized board, with queens represented by "Q".
2. **Solution Board** shows the final solution after applying the Hill Climbing algorithm. The queens are placed such that no two queens are attacking each other.

---

## **Time Complexity**

The time complexity of the Hill Climbing Algorithm in this case is approximately **O(n^4)**. This is due to the need to evaluate the heuristic (number of attacks) for each possible move (n possible moves per queen, for n queens). Although Hill Climbing is efficient in some cases, it can become computationally expensive for larger values of N due to the need to explore many possible configurations.

---

## **Limitations & Future Improvements**

### **Limitations:**
1. **Local Optima:** The algorithm may get stuck in a local optimum, where no further improvements can be made, even though the global solution is still out of reach. This is addressed by retrying with a new random board after several failed attempts.
2. **Performance:** The time complexity can grow rapidly for large values of N (e.g., N > 10), making the solution less efficient for larger boards.

### **Future Improvements:**
1. **Simulated Annealing:** Implementing Simulated Annealing could help overcome the local optimum problem.
2. **Genetic Algorithms:** A population-based search technique like Genetic Algorithms could be used to explore multiple solutions simultaneously and converge faster.
3. **Optimization:** Further optimization of the heuristic calculation could potentially improve performance for larger boards.

---

## **Installation Instructions**

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/n-queen-hill-climbing.git
   ```

2. **Run the Code:**
   - Ensure you have Python 3.x installed on your system.
   - Run the script using the following command:
     ```bash
     python nqueen_hill_climbing.py
     ```

3. **Input:**
   - You will be prompted to enter the number of queens for the board (e.g., `4` for a 4×4 board).

---

## **Conclusion**

This project demonstrates how the Hill Climbing algorithm can be applied to solve the N-Queen problem. It provides a practical example of local search techniques in artificial intelligence and showcases the challenges of dealing with local optima and solution convergence in optimization problems.


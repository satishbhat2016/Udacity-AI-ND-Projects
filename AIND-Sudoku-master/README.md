# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A:
    * Naked Twins strategy looks for two squares in the same unit that both have the same two possible digits
    * First step is to eliminnate these identical sets - naked twins from the boxes
    * once these NT are eliminated it is possible that some boxes will have automatically single digits assigned (solved) values
      by simplifying the solution
    * In order to solve the sudoku problem ensuring that the program is not stalled (by entering into never ending search logic),
      other constraints such as eliminate, only_choice strategies are applied along with naked_twins logic.


# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A:
   * Constraint propogation is used to reduce search iterations to ensure that solution can be reached with no extensive searching and matching.
   * Key logic used to identify boxes contained in two diagonal units.
   * To reduce the search heuristic constraint propogation is applied to two additional diagonals - on top of squares, rows and columns

   To solve the given sudoku problem:
   * Define the diagonals and make it as an additonal unit
      diagonal_units = [[x+y for x, y in zip(rows, cols)], [x+y for x, y in zip(rows, cols[::-1])]]

   * Add it to the unitlists, units and to peers so that all diagonal units will have diagonal peers
   * Now, in the program identify the boxes related to two diagonal units and apply the constraints (row, column and square units)
     to solve the problem

   

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solution.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py


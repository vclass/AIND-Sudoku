# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: We create constraint for naked twins problem and include in reduce_puzzle step as below:-
    We create list of instances of naked twins pair by using 3 conditions:
        1. They are peer of each other
        2. Their values are 2 digits
        3. They are identical
    Then, loop through list of instances, eliminate the naked twins as possibilities for their peers
    Finally, we included Naked Twins constrain into reduce_puzzle function

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: We create another unit called "diagonal_units" that consist of 2 units:-
    1. topleft-to-bottomright diagonal
    2. bottomleft-to-topright diagonal
   Then, add it to unitlist. With this way, all constraint propagation we wrote will include diagonal constraint

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.
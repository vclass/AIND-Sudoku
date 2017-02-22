# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Naked Twins technique is one of Suduko strategies to eliminate/reduce possibilities.
   When we have twin boxes appear in the same units (square, column, or row), it is obvious that the 2 digits in the
   twins need to be placed only in these 2 boxes although we don't know which digit should be placed in each box.
   So, we can exclude possibilities of these 2 digits from other boxes in the same units.

   We can use constraint propagation technique to implement the naked twins strategy with 2 steps below:-

    1. Find Naked Twins: Create list of instances of naked twins by looping through all units.
    The pair of boxes is considered naked twin when they satisfy these 3 conditions:
        1. They are peer of each other
        2. Their values are 2 digits
        3. They are identical
    2. Eliminate possibilities: Loop through list of Naked Twins, for each unit Naked Twins belong to, eliminate
    the naked twins as possibilities from their peers.

    Finally, we included Naked Twins constraint into Problem Reduction step (reduce_puzzle function) along
    with Elimination and Only Choice constraints. This help the agent to solve the problem faster as the technique help
    eliminate more possibilities, so, reduce the size of Search Space.


# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: For normal Sudoku, there are 3 rules to fill out digits into puzzle:
   1. Rows need to have all digits from 1 - 9 without duplication
   2. Columns need to have all digits from 1 - 9 without duplication
   3. Squares need to have all digits from 1 - 9 without duplication

   For Sudoku solving agent, we implement constraints propagation techniques based on these 3 rules. We implement techniques
   that can eliminate possibilities to fill in the digits that will violate the rule. For example, the naked twins strategy
   mentioned above eliminate naked twins from their peers because if we don't fill those only 2 possible digits in naked twin
   , we will need to leave them blank and will violate a rule.

   For diagonal Sudoku, there is additional rule below:
   4. Diagonal axis (Both topleft-to-bottomright diagonal and bottomleft-to-topright diagonal) need to have all digits
   from 1 - 9 without duplication

   For Diagonal Sudoku solving agent, we need to adjust codes to ensure that all constraint propagation techniques we
   implemented satisfied the new rule as well. The implementation steps are below:-
        1. Create another unit called "diagonal_units" that consist of 2 units:-
           1. TopLeft-to-BottomRight diagonal - [A1, B2, C3, D4, E5, F6, G7, H8, I9]
           2. BottomLeft-to-TopRight diagonal - [A9, B8, C7, D6, E5, F4, G3, H2, I1]
        2. Include diagonal_units into list of units (unitlist = row_units + column_units + square_units + diagonal_units)
        With this way, all constraint propagation techniques we wrote before will include diagonal rule into consideration.

   As Diagonal rule create more constraints to the puzzle, constraint propagation will be able to eliminate more possibilities
   in Problem Reduction step. This means Sudoku Solving Agent should be able to solve the problem faster as Search Space
   is smaller from constraint propagation.

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
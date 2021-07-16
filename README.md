# Sudoku dectector and solver #

We can solve a vaid sudoku puzzle using backtracking algorithm. But wouldn't it be cool if we could take a pic of the puzzle, solve it and show the solved grid? 
We use the opencv library to find the sudoku grid and capture only the essential part within the image. TensorFlow keras API can be used to train the model for recognizing digits.

Broad steps involved                                     |
--------------                                           |
1. | Loading the input image                             |
2. | Localize the sudoku grid                            |
3. | Localize each of 81 cells in the grid               |
4. | Determine if cell is blank, else predict the digit  |
5. | Solve the grid using backtracking algorithm         |
6. | Display solved puzzle                               |


## Preprocessing the image ##




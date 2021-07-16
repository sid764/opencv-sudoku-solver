# Sudoku dectector and solver #

We can solve a vaid sudoku puzzle using backtracking algorithm. But wouldn't it be cool if we could take a pic of the puzzle, solve it and show the solved grid? 
We use the opencv library to find the sudoku grid and capture only the essential part within the image. TensorFlow keras API can be used to train the model for recognizing digits.

Broad steps involved                                |
--------------                                      |
Loading the input image                             |
Localize the sudoku grid                            |
Localize each of 81 cells in the grid               |
Determine if cell is blank, else predict the digit  |
Solve the grid using backtracking algorithm         |
Display solved puzzle                               |


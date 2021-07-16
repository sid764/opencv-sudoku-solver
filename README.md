# Sudoku dectector and solver #

We can solve a vaid sudoku puzzle using backtracking algorithm. But wouldn't it be cool if we could take a pic of the puzzle, solve it and show the solved grid? 
We use the opencv library to find the sudoku grid and capture only the essential part within the image. TensorFlow keras API can be used to train the model for recognizing digits.

Broad steps involved                                   |
--------------                                         |
a) Loading the input image                             |
b) Localize the sudoku grid                            |
c) Localize each of 81 cells in the grid               |
d) Determine if cell is blank, else predict the digit  |
e) Solve the grid using backtracking algorithm         |
f) Display solved puzzle                               |


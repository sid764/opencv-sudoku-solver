# Sudoku dectector and solver #

We can solve a vaid sudoku puzzle using backtracking algorithm. But wouldn't it be cool if we could take a pic of the puzzle, solve it and show the solved grid? 
We use the opencv library to find the sudoku grid and capture only the essential part within the image. TensorFlow keras API can be used to train the model for recognizing digits.

Broad steps involved                                    |
--------------                                          |
1.  Loading the input image                             |
2.  Localize the sudoku grid                            |
3.  Localize each of 81 cells in the grid               |
4.  Determine if cell is blank, else predict the digit  |
5.  Solve the grid using backtracking algorithm         |
6.  Display solved puzzle                               |


## Sample input ##

<img src="https://user-images.githubusercontent.com/60272094/125901417-e59c881d-3210-4426-9b79-a49017806372.JPG" width="400" height="350">


### Preprocessing input image ###

The image is resized to 450 x 450 and converted to grayscale. To extract more prominent features, we do a Gaussian blur on the image. Then thresholding is done to separate desirable foreground image parts from the background. We use adaptive thresholding so threshold values will be different for different regions based on pixel intensities. After preprocessing, image will be

![step1](https://user-images.githubusercontent.com/60272094/125901663-ca399597-af97-4418-a28d-d31b8c39f2b0.JPG)

### Detecting contours ###


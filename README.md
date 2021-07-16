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


## Sample input ##

<img src="https://user-images.githubusercontent.com/60272094/125901417-e59c881d-3210-4426-9b79-a49017806372.JPG" width="400" height="350">


### Preprocessing input image ###

The image is resized to 450 x 450 and converted to grayscale. To extract more prominent features, we do a Gaussian blur on the image. Then thresholding is done to separate desirable foreground image parts from the background. We use adaptive thresholding so threshold values will be different for different regions based on pixel intensities. After preprocessing, image will be

<img src="https://user-images.githubusercontent.com/60272094/125901663-ca399597-af97-4418-a28d-d31b8c39f2b0.JPG" width="400" height="350">

### Contour detection ###

In the preprocessed image, all contours are detected using findContours() function. Then we approximate the contour to a polygon and find its area using inbuilt functions in opencv. The approxPolyDP() function returns the set of vertices of a contour with the value of epsilon we specify. Epsilon value means the threshold for determining the distance between two points. Smaller the value of epsilon, the more closer will be the polygon to the shape of the contour and the number of edges will be larger if the contour had a curvy nature. 

<img src="https://user-images.githubusercontent.com/60272094/125903778-33691b5a-1da5-4d80-af86-568e87957819.JPG" width="400" height="350">

The 4-sided contour with largest area will be considered as the sudoku grid. We then arrange the vertices in order. We have found out the four vertices of the grid. This part of the image will be warped to the original size of the image.

<img src="https://user-images.githubusercontent.com/60272094/125904393-97ae21c5-0387-4379-a96c-0aa4e6e0f714.JPG" width="400" height="350">

### Training the model ###

I did not use the MNIST dataset for digit classification because it contains handwritten digits which are way different from printed digits we see in a sudoku puzzle. The dataset is from http://www.ee.surrey.ac.uk/CVSSP/demos/chars74k/. Keras Sequential model was used for training. Data augmentation was also applied to training set images. 

Summary of the model:

<img src="https://user-images.githubusercontent.com/60272094/125906446-676997ae-c4e3-4a83-9d52-c4aa8f774a72.JPG", width="500" height="800">

















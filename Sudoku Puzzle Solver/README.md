
## Sudoku Puzzle Solver

NOTEBOOK DEMO:  [![Nbviewer](https://github.com/jupyter/design/blob/main/logos/Badges/nbviewer_badge.svg)](https://nbviewer.jupyter.org/github/shejz/OCR/blob/main/Sudoku%20Puzzle%20Solver/opencv_sudoku_solver.ipynb)


### A digit OCR model implemented in Keras and TensorFlow

Every Sudoku puzzle starts with an NxN grid (typically 9×9) where some cells are blank and other cells already contain a digit. But before we can solve Sudoku puzzles with OpenCV, we first need to implement a neural network architecture that will handle OCR’ing the digits on the Sudoku puzzle board. Perhaps unsurprisingly, we’ll be using the **MNIST** dataset to train our digit recognizer.

### Steps for building an OpenCV-based Sudoku puzzle solver that uses Optical Character Recognition (OCR) to recognize digits.

![](https://github.com/shejz/OCR/blob/main/Sudoku%20Puzzle%20Solver/soduko_pipeline.jpg)

**Sudoku puzzle solver 6-step process**:
1. Provide input image containing Sudoku puzzle to our system.
2. Locate where in the input image the puzzle is and extract the board.
3. Given the board, locate each of the individual cells of the Sudoku board (most standard Sudoku puzzles are a 9×9 grid, so we’ll need to localize each of these cells).
4. Determine if a digit exists in the cell, and if so, OCR it.
5. Apply a Sudoku puzzle solver/checker algorithm to validate the puzzle.
6. Display the output result to the user.

In order to find and locate the Sudoku puzzle board in the image, we utilized OpenCV and basic image processing techniques, including blurring, thresholding, and contour processing, just to name a few.

To actually OCR the digits on the Sudoku board, we trained a custom digit recognition model using Keras and TensorFlow. Combining the Sudoku board locator with our digit OCR model allowed us to make quick work of solving the actual Sudoku puzzle.

### Model Architecture

The body of our network is composed of:

- CONV => RELU => POOL: Layer set 1
- CONV => RELU => POOL: Layer set 2
- FC => RELU: Fully-connected layer set with 50% dropout

The head of the network consists of a softmax classifier with the number of outputs being equal to the number of our classes (in our case: 10 digits).

![](https://github.com/shejz/OCR/blob/main/Sudoku%20Puzzle%20Solver/output/digit_classifier.h5.png)

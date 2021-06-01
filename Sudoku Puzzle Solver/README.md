
## Sudoku Puzzle Solver

NOTEBOOK DEMO:  [![Nbviewer](https://github.com/jupyter/design/blob/master/logos/Badges/nbviewer_badge.svg)](https://nbviewer.jupyter.org/github/shejz/OCR/blob/main/Sudoku%20Puzzle%20Solver/opencv_sudoku_solver.ipynb)

### Steps for building an OpenCV-based Sudoku puzzle solver that uses Optical Character Recognition (OCR) to recognize digits.

![](https://github.com/shejz/OCR/blob/main/Sudoku%20Puzzle%20Solver/soduko_pipeline.jpg)

In order to find and locate the Sudoku puzzle board in the image, we utilized OpenCV and basic image processing techniques, including blurring, thresholding, and contour processing, just to name a few.

To actually OCR the digits on the Sudoku board, we trained a custom digit recognition model using Keras and TensorFlow. Combining the Sudoku board locator with our digit OCR model allowed us to make quick work of solving the actual Sudoku puzzle.

### Model Architecture

![](https://github.com/shejz/OCR/blob/main/Sudoku%20Puzzle%20Solver/output/digit_classifier.h5.png)

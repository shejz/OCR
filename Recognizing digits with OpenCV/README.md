## Recognizing Digits 

NOTEBOOK DEMO:  [![Nbviewer](https://github.com/jupyter/design/blob/master/logos/Badges/nbviewer_badge.svg)](https://nbviewer.jupyter.org/github/shejz/OCR/blob/main/Recognizing%20digits%20with%20OpenCV/recognize_digits.ipynb)

### The seven-segment display
You’re likely already familiar with a seven-segment display, even if you don’t recognize the particular term. A great example of such a display is your classic digital alarm clock

**Each digit on the alarm clock is represented by a seven-segment component just like the one below**:

![](https://github.com/shejz/OCR/blob/main/Recognizing%20digits%20with%20OpenCV/seven-segment.jpg)


We’ll be using the **thermostat** image as input:

![](https://github.com/shejz/OCR/blob/main/Recognizing%20digits%20with%20OpenCV/thermostat.jpg)

**Whenever I am trying to recognize/identify object(s) in an image I first take a few minutes to assess the problem. Given that my end goal is to recognize the digits on the LCD display I know I need to:**:
1. Localize the LCD on the thermostat. This can be done using edge detection since there is enough contrast between the plastic shell and the LCD.
2. Extract the LCD. Given an input edge map I can find contours and look for outlines with a rectangular shape — the largest rectangular region should correspond to the LCD. A perspective transform will give me a nice extraction of the LCD.
3. Extract the digit regions. Once I have the LCD itself I can focus on extracting the digits. Since there seems to be contrast between the digit regions and the background of the LCD I’m confident that thresholding and morphological operations can accomplish this.
4. Identify the digits. Recognizing the actual digits with OpenCV will involve dividing the digit ROI into seven segments. From there I can apply pixel counting on the thresholded image to determine if a given segment is “on” or “off”.

### Pre-process the image

- Resizing it.
- Converting the image to grayscale.
- Applying Gaussian blurring with a 5×5 kernel to reduce high-frequency noise.
- Computing the edge map via the Canny edge detector.

After applying these pre-processing steps our edge map looks like this:

![](https://github.com/shejz/OCR/blob/main/Recognizing%20digits%20with%20OpenCV/gray-scale.jpg)

Notice how the outlines of the LCD are clearly visible — this accomplishes Step #1.

In order to find the LCD regions, we need to extract the contours (i.e., outlines) of the regions in the edge map. 

Applying the perspective transform gives us a top-down, birds-eye-view of the LCD:

![](https://github.com/shejz/OCR/blob/main/Recognizing%20digits%20with%20OpenCV/transformed.jpg)

Obtaining this view of the LCD satisfies Step #2 — we are now ready to extract the digits from the LCD.



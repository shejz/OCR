# **Text localization and detection**

Text detection is the process of localizing where an image text is. In text detection, our goal is to automatically compute the bounding boxes for every region of text in an image.

## **How to utilize Tesseract to detect, localize, and OCR text**

This method was a three stage process:
1. Use OpenCV's EAST text detection model to detect the presence of text in an image.
2. Extract the text Region of Interest (ROI) from the image using basic image cropping/NumPy array slicing.
3. Take the text ROI, and then pass it into Tesseract to actually OCR the text.

The benefit of using **Tesseract** to perform text detection and OCR is that we can do so in just a `single function call`, making it easier than the multistage OpenCV OCR process above.



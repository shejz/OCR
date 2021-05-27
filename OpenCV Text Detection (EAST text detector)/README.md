 ## OpenCV’s new EAST text detector to automatically detect the presence of text in natural scene images.
 
 DEMO:  [![Nbviewer](https://github.com/jupyter/design/blob/master/logos/Badges/nbviewer_badge.svg)](https://nbviewer.jupyter.org/github/shejz/OCR/blob/main/OpenCV%20Text%20Detection%20%28EAST%20text%20detector%29/opencv_EAST_text_detection.ipynb)
 
 ### The algorithm “EAST”: Efficient and Accurate Scene Text Detection. 
 The EAST pipeline is capable of predicting words and lines of text at arbitrary orientations on 720p images, and furthermore, can run at 13 FPS.
 
 > OpenCV’s EAST text detector is a deep learning model, based on a novel architecture and training pattern. It is capable of:
 1. Running at near real-time at 13 FPS on 720p images 
 2. Obtains state-of-the-art text detection accuracy.

### Why detecting text in natural scene images can be so challenging.
- Image/sensor noise: Sensor noise from a handheld camera is typically higher than that of a traditional scanner. Additionally, low-priced cameras will typically interpolate the pixels of raw sensors to produce real colors.
- Viewing angles: Natural scene text can naturally have viewing angles that are not parallel to the text, making the text harder to recognize.
- Blurring: Uncontrolled environments tend to have blur, especially if the end user is utilizing a smartphone that does not have some form of stabilization.
- Lighting conditions: We cannot make any assumptions regarding our lighting conditions in natural scene images. It may be near dark, the flash on the camera may be on, or the sun may be shining brightly, saturating the entire image.
- Resolution: Not all cameras are created equal — we may be dealing with cameras with sub-par resolution.
- Non-paper objects: Most, but not all, paper is not reflective (at least in context of paper you are trying to scan). Text in natural scenes may be reflective, including logos, signs, etc.
- Non-planar objects: Consider what happens when you wrap text around a bottle — the text on the surface becomes distorted and deformed. While humans may still be able to easily “detect” and read the text, our algorithms will struggle. We need to be able to handle such use cases.
- Unknown layout: We cannot use any a priori information to give our algorithms “clues” as to where the text resides.

**OpenCV’s text detector implementation of EAST is quite robust, capable of localizing text even when it’s blurred, reflective, or partially obscured**


### Video text detection results
![](https://github.com/shejz/OCR/blob/main/OpenCV%20Text%20Detection%20(EAST%20text%20detector)/output.gif)

The text detector is not only accurate, but it’s capable of running in near real-time at approximately 13 FPS on 720p images.

In order to provide an implementation of OpenCV’s EAST text detector, I needed to convert [OpenCV’s C++ example](https://github.com/opencv/opencv/blob/master/samples/dnn/text_detection.cpp); however, there were a number of challenges I encountered, such as:

- Not being able to use OpenCV’s `NMSBoxes`  for non-maxima suppression and instead having to use my implementation from `imutils` .
- Not being able to compute a true rotated bounding box due to the lack of Python bindings for `RotatedRect` .

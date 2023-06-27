
## OCR: Handwriting recognition with OpenCV, Keras, and TensorFlow

NOTEBOOK DEMO:  [![Nbviewer](https://github.com/jupyter/design/blob/main/logos/Badges/nbviewer_badge.svg)](https://nbviewer.jupyter.org/github/shejz/OCR/blob/main/Handwriting%20Recognition/ocr_handwriting_recognition.ipynb)

 Handwriting recognition tends to be significantly harder than traditional OCR that uses specific fonts/characters. The reason this concept is so challenging is that unlike computer fonts, there are nearly infinite variations of handwriting styles. Every one of us has a personal style that is specific and unique.

The model obtained 96% accuracy on the testing set for handwriting recognition.

### Image Preprocessing

The handwriting recognition system utilized basic computer vision and image processing algorithms (edge detection, contours, and contour filtering) to segment characters from an input image.

![](https://github.com/shejz/OCR/blob/main/Handwriting%20Recognition/image%20pre-processing.jpg)

### Limitations

While the handwriting recognition model obtained **96%** accuracy on our testing set, our handwriting recognition accuracy on our own custom images is slightly less than that. 

One of the biggest issues is that we used variants of the MNIST (digits) and NIST (alphabet characters) datasets to train our handwriting recognition model. These datasets, while interesting to study, don’t necessarily translate to real-world projects because the images have already been pre-processed and cleaned for us — **real-world characters aren’t that “clean.”**. Additionally, our handwriting recognition method requires characters to be individually segmented. That may be possible for some characters, but many of us (especially cursive writers) connect characters when writing quickly. This confuses our model into thinking a group of characters is actually a single character, which ultimately leads to the incorrect results.

While the handwriting recognition model performed well on the training and testing set, the architecture — combined with the training dataset itself — is not robust enough to generalize as an “off-the-shelf” handwriting recognition model. To improve our handwriting recognition accuracy, we should look into advances in **Long Short-term Memory networks (LSTMs)**, which can naturally handle connected characters.





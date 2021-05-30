
[EasyOCR for Optical Character Recognition](https://github.com/shejz/OCR/tree/main/EasyOCR%20for%20Optical%20Character%20Recognition)

The EasyOCR is a Python package that allows computer vision developers to effortlessly perform Optical Character Recognition.

[Tesseract OCR](https://github.com/shejz/OCR/tree/main/Tesseract%20OCR)

The biggest downside is with the limitations of Tesseract itself. Tesseract works best when there are extremely clean segmentations of the foreground text from the background.

Furthermore these segmentations need to be as high resolution (DPI) as possible and the characters in the input image cannot appear “pixelated” after segmentation. If characters do appear pixelated then Tesseract will struggle to correctly recognize the text — we found this out even when applying images captured under ideal conditions (a PDF screenshot).

[Tesseract OCR for Non-English Languages](https://github.com/shejz/OCR/tree/main/Tesseract%20OCR%20for%20Non-English%20Languages)

 OCR non-English languages using the Tesseract OCR engine.

[Text localization and detection](https://github.com/shejz/OCR/tree/main/Text%20localization%20and%20detection)

Tesseract to detect text, localize it, and then OCR it.

The benefit of using Tesseract to perform text detection and OCR is that we can do so in just a single function call, making it easier than the multistage OpenCV OCR process.

[OpenCV Text Detection using EAST text detector](https://github.com/shejz/OCR/tree/main/OpenCV%20Text%20Detection%20(EAST%20text%20detector))

Detect text in natural scene images using the EAST text detector.

[Credit card OCR with OpenCV](https://github.com/shejz/OCR/tree/main/Credit%20card%20OCR%20with%20OpenCV)

Perform Optical Character Recognition (OCR) using template matching via OpenCV. Specifically, we applied our template matching OCR approach to recognize the type of a credit card along with the 16 credit card digits.

[OCR Bank Check](https://github.com/shejz/OCR/tree/main/OCR%20Bank%20Check)

OCR'ing a bank check is more difficult than OCR’ing a credit card — this is mainly due to the fact that bank check symbols consist of multiple parts. Back check OCR to images using OpenCV and Template Matching. In fact, this is the same method that we used for credit card OCR the primary difference is that we had to take special care to extract each **MICR E-13B** symbol, especially when these symbols contain multiple contours.

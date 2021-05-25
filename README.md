


[Tesseract OCR](https://github.com/shejz/OCR/tree/main/Tesseract%20OCR)

The biggest downside is with the limitations of Tesseract itself. Tesseract works best when there are extremely clean segmentations of the foreground text from the background.

Furthermore these segmentations need to be as high resolution (DPI) as possible and the characters in the input image cannot appear “pixelated” after segmentation. If characters do appear pixelated then Tesseract will struggle to correctly recognize the text — we found this out even when applying images captured under ideal conditions (a PDF screenshot).

[Text localization and detection](https://github.com/shejz/OCR/tree/main/Text%20localization%20and%20detection)

Tesseract to detect text, localize it, and then OCR it.

The benefit of using Tesseract to perform text detection and OCR is that we can do so in just a single function call, making it easier than the multistage OpenCV OCR process.

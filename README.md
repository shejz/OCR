


## [Tesseract OCR](https://github.com/shejz/OCR/tree/main/Tesseract%20OCR)

**Limitations of Tesseract for OCR**
- Tesseract is best suited for situations with high resolution inputs where the foreground text is cleanly segmented from the background.

> Furthermore these segmentations need to be as high resolution (DPI) as possible and the characters in the input image cannot appear “pixelated” after segmentation. If characters do appear pixelated then Tesseract will struggle to correctly recognize the text found this out even when applying images captured under ideal conditions (a PDF screenshot).

**RESULTS**

1. **Noisy Image**: This image contains our desired foreground black text on a background that is partly white and partly scattered with artificially generated circular blobs. The blobs act as “distractors” to our simple algorithm.

![](https://github.com/shejz/OCR/blob/main/Tesseract%20OCR/results/noisy.jpg)

2. **Salt and pepper noise in the background**: Unfortunately, Tesseract did not successfully OCR the text in the left image. However, by using the **blur** pre-processing method right image can obtain better results.

![](https://github.com/shejz/OCR/blob/main/Tesseract%20OCR/results/Salt%20and%20pepper%20noise.jpg)

4. Finally, let’s try another image, this one with more text. Screenshot from pdf files.

![](https://github.com/shejz/OCR/blob/main/Tesseract%20OCR/results/book-section.jpg)




## [Text localization and detection](https://github.com/shejz/OCR/tree/main/Text%20localization%20and%20detection)

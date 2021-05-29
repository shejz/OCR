
Bank check OCR I

OCR'ing a bank check is more difficult than OCR’ing a credit card — this is mainly due to the fact that bank check symbols consist of multiple parts.

We cannot assume that each contour in our reference font image maps to an individual character.

Instead, we need to insert extra logic that examines the dimensions of each contour and determines if we are examining a digit or a symbol.

In the case that we have found a symbol, we need to grab the next two contours to build our bounding box (since a bank check control character consists of three distinct parts).

Since OCR'ing a bank check with OpenCV and Python is much more complicated than OCR’ing a credit card

1. The **MICR E-13B** font, used by countries including the United States, United Kingdom, Canada, and others for check recognition.
2. Extract both the digits and symbols from a **MICR E-13B** reference image. This will enable us to extract ROIs for each of the characters and later use them to OCR a bank check. We'll accomplish this using OpenCV contours and a bit of Python iterator “magic”.

![](https://github.com/shejz/OCR/blob/main/OCR%20Bank%20Check/Bank%20Check%20OCR%20Part%20I/iterator%20magic.jpg)


The MICR E-13B font, commonly used for bank check recognition. We’ll be OCR’ing this bank check font using OpenCV
![](https://github.com/shejz/OCR/blob/main/OCR%20Bank%20Check/Bank%20Check%20OCR%20Part%20I/MICR%20E-13B%20font.jpg)


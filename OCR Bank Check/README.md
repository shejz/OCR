
## Bank Check OCR I

DEMO:  [![Nbviewer](https://github.com/jupyter/design/blob/master/logos/Badges/nbviewer_badge.svg)](https://nbviewer.jupyter.org/github/shejz/OCR/blob/main/OCR%20Bank%20Check/Bank%20Check%20OCR%20Part%20I/bank_check_ocr.ipynb)

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

**MICR (Magnetic Ink Character Recognition)** is a financial industry technology for processing documents. You will often find this magnetic ink in the E-13B format on the bottom of account statements and checks.

The E-13B variant of MICR contains 14 characters:

- **numerals**: digits 0-9
- ⑆ **transit**: bank branch delimiter
- ⑇ **amount**: transaction amount delimiter
- ⑈ **on-us**: customer account number delimiter
- ⑉ **dash**: number delimiter (between routing and account number, for example)

## Bank Check OCR II

DEMO:  [![Nbviewer](https://github.com/jupyter/design/blob/master/logos/Badges/nbviewer_badge.svg)](https://nbviewer.jupyter.org/github/shejz/OCR/blob/main/OCR%20Bank%20Check/Bank%20Check%20OCR%20Part%20II/bank_check_ocr_part_ii.ipynb)

In part I we apply back check OCR to images using OpenCV and template matching. In fact, this is the same method that we used for credit card OCR — the primary difference is that we had to take special care to extract each **MICR E-13B** symbol, especially when these symbols contain multiple contours. 

However, while our template matching method worked correctly on this particular example image, real-world inputs are likely to be much more noisy, making it harder for us to extract the digits and symbols using simple contour techniques. In these situations, it would be best to localize each of the digits and characters followed by applying machine learning to obtain higher digit classification accuracy. Methods such as Histogram of Oriented Gradients + Linear SVM and deep learning will obtain better digit and symbol recognition accuracy on real-world images that contain more noise.

![](https://github.com/shejz/OCR/blob/main/OCR%20Bank%20Check/Bank%20Check%20OCR%20Part%20II/check_ocr.png)

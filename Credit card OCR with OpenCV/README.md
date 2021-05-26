## **OCR via template matching using OpenCV**

### **The OCR-A font**
The OCR-A font, a font created specifically to aid Optical Character Recognition algorithms. Commonly found on the front of credit/debit cards.

We’ll then devise a computer vision and image processing algorithm that can:

1. Localize the four groupings of four digits on a credit card.
2. Extract each of these four groupings followed by segmenting each of the sixteen numbers individually.
3. Recognize each of the sixteen credit card digits by using template matching and the OCR-A font.

### **Template matching**
As a form of OCR to create a solution to automatically recognize credit cards and extract the associated credit card digits from images.

#### **Image processing pipeline**
1. Detect the location of the credit card in the image and the four groups of four numbers on the credit card via various image processing techniques, including morphological operations, thresholding, and contour extraction.
2. Localize the four groupings of four digits, pertaining to the sixteen digits on the credit card.
3. Applying template matching to each digit by comparing it to the OCR-A font to obtain our digit classification.
4. Examining the first digit of the credit card number to determine the issuing company. Recognize the type of credit card (i.e., Visa, MasterCard, American Express, etc.).

**Sample Output**

![](https://github.com/shejz/OCR/blob/main/Credit%20card%20OCR%20with%20OpenCV/output/output.jpg)


After evaluating our credit card OCR system, we found it to be 100% accurate provided that the issuing credit card company used the OCR-A font for the digits.

To extend this application, you would want to gather real images of credit cards in the wild and potentially train a machine learning model (either via standard feature extraction or training or Convolutional Neural Network) to further improve the accuracy of this system.

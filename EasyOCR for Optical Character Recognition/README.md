## EasyOCR for Optical Character Recognition

DEMO:  [![Nbviewer](https://github.com/jupyter/design/blob/main/logos/Badges/nbviewer_badge.svg)](https://nbviewer.jupyter.org/github/shejz/OCR/blob/main/EasyOCR%20for%20Optical%20Character%20Recognition/easy_ocr.ipynb)

**Optical Character Recognition (OCR) is made easy with the EasyOCR Python package**.

- The EasyOCR package can be installed with a single pip command.
- The dependencies on the EasyOCR package are minimal, making it easy to configure your OCR development environment.
- Once EasyOCR is installed, only one `import` statement is required to import the package into your project.
- From there, all you need is two lines of code to perform OCR — one to initialize the `Reader` class and then another to OCR the image via the `readtext` function.

**EasyOCR has a number of benefits going for it**:
1. You can use your GPU to increase the speed of your Optical Character Recognition pipeline.
2. You can use EasyOCR to OCR text in multiple languages at the same time.
3. The EasyOCR API is Pythonic, making it simple and intuitive to use.

EasyOCR is implemented using Python and the PyTorch library. If you have a CUDA-capable GPU, the underlying PyTorch deep learning library can speed up your text detection and OCR speed tremendously.

### EasyOCR Results
![](https://github.com/shejz/OCR/blob/main/EasyOCR%20for%20Optical%20Character%20Recognition/Results.jpg)

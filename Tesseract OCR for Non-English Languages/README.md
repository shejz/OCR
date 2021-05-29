## Tesseract Optical Character Recognition (OCR) for Non-English Languages

**Setup**:
- Configure the Tesseract OCR engine for multiple languages, including non-English languages.
- Download multiple language packs for Tesseract and verify that it works properly — we’ll use German as an example case.
- Configure the TextBlob package, which will be used to translate from one language into another.

Most Tesseract installs will naturally handle multiple languages with no additional configuration; however, in some cases you will need to:
1. Manually download Tesseract’s language packs manually from GitHub and install them.
2. Set the TESSDATA_PREFIX environment variable to point the language packs
3. Verify that the language packs directory is correct

### Project Structure
1. Accept an input image
2. Detect and OCR text in non-English languages
3. Translate the OCR’d text from the given input language into English
4. Display the results to our terminal

### Language Packs to Tesseract OCR

Tesseract OCR supports a wide array of languages. In fact, Tesseract supports over 100 languages, including those that comprise characters and symbols, as well as right-to-left languages such as Arabic and Hebrew.


### Tesseract OCR and Non-English Languages Results




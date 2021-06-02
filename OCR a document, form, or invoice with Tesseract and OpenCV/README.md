
## OCR a document, form, or invoice

Despite living in the digital age, we still have a strong reliance on physical paper trails, especially in large organizations such as government, enterprise companies, and universities/colleges.

The need for physical paper trails combined with the fact that nearly every document needs to be organized, categorized, and even shared with multiple people in an organization requires that we also digitize the information on the document and save it in our databases. These large organizations employ data entry teams whose sole purpose is to take these physical documents, manually re-type the information, and then save it into the system.

Optical Character Recognition algorithms can automatically digitize these documents, extract the information, and pipe them into a database for storage, alleviating the need for large, expensive, and even error-prone manual entry teams.

### Steps to implementing a document OCR pipeline
1.  Involves defining the locations of fields in the input image document. Determine the bounding box (x, y)-coordinates of each field we want to OCR as shown below

![](https://github.com/shejz/OCR/blob/main/OCR%20a%20document%2C%20form%2C%20or%20invoice%20with%20Tesseract%20and%20OpenCV/Steps/Step1.%20Specifying%20Locations.jpg)

2. Then we accept an input image containing the document we want to OCR and present it to our OCR pipeline.
![](https://github.com/shejz/OCR/blob/main/OCR%20a%20document%2C%20form%2C%20or%20invoice%20with%20Tesseract%20and%20OpenCV/Steps/Step2.%20Input%20image%20containing%20the%20document.jpg)
4. Apply automatic image alignment/registration to align the input image with the template form. Aligning a scanned document with its template using OpenCV.
5. Loops over all text field locations (which we defined in Step #1), extracts the ROI, and applies OCR to the ROI. It’s during this step that we’re able to OCR the text itself and associate it with a text field in the original template document demonstrated. **(Knowing the form field locations from Step #1 allows us to perform Step #4, which consists of extracting ROIs from our aligned document and accomplishing OCR)**
6. Knowing the form field locations from Step #1 allows us to perform Step #4, which consists of extracting ROIs from our aligned document and accomplishing OCR. The final Step #5 is to display our output OCR’d document depicted.
![](https://github.com/shejz/OCR/blob/main/OCR%20a%20document%2C%20form%2C%20or%20invoice%20with%20Tesseract%20and%20OpenCV/Steps/Step5.%20Output.jpg)


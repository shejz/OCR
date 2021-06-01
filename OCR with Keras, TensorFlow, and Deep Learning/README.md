## Optical Character Recognition (OCR) model using Keras, TensorFlow, and Deep Learning

1. [Training an OCR model with Keras and TensorFlow](https://github.com/shejz/OCR/tree/main/OCR%20with%20Keras%2C%20TensorFlow%2C%20and%20Deep%20Learning) 
2. [Handwriting Recognition with Keras and TensorFlow](https://github.com/shejz/OCR/tree/main/Handwriting%20Recognition)

### Implement and train a custom OCR model with Keras and TensorFlow.
Train a custom Keras/TensorFlow model to recognize alphanumeric characters (i.e., the digits 0-9 and the letters A-Z). And we can use this model to correctly classify handwritten characters in custom input images.

### Deep Learning OCR datasets

**In order to train our custom Keras and TensorFlow model, we’ll be utilizing two datasets**:
1. The standard MNIST 0-9 dataset by LeCun et al.
2. The Kaggle A-Z dataset by Sachin Patel, based on the NIST Special Database 19

![](https://github.com/shejz/OCR/blob/main/OCR%20with%20Keras%2C%20TensorFlow%2C%20and%20Deep%20Learning/ocr_datasets.jpg)

### Keras and TensorFlow OCR training results
- Loads MNIST 0-9 digits and Kaggle A-Z letters.
- Trains a **ResNet** model on the dataset

As you can see, our Keras/TensorFlow OCR model is obtaining ~96% accuracy on the testing set.

The training history can be seen below at left side and we can see also on the right our sample output that our Keras and TensorFlow OCR model is performing quite well in identifying our character set.

![](https://github.com/shejz/OCR/blob/main/OCR%20with%20Keras%2C%20TensorFlow%2C%20and%20Deep%20Learning/results.jpg)

As evidenced by the plot, there are few signs of overfitting, implying that our Keras and TensorFlow model is performing well at our basic OCR task.

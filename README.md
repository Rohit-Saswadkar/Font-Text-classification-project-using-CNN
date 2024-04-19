For any concerns or queries please connect - saswadkar.rohit1@gmail.com .


Link to Presentation - https://docs.google.com/presentation/d/1lPR56_HoAeXm3Z0hbDfN4gOu1s7L1wtn/edit?usp=sharing&ouid=115169350078482455358&rtpof=true&sd=true
* Thank you to giving m this valuable opportunity which reulted to learn about Cv2 and more about CNN

Installation required libraries - 
* 1] install tensorflow
* 2] install cv2
* 3] install easyocr

Dataset used - Font Recognition Data
This data consists to types od datasets - 1] font dataset large   2] Font dataset large color
I used "Font dataset large" as I trained the model in my laptop (due to google drive folder upload time constraints) so to avoid processing load I usec that dataset.


Text Detection and Font Recognition Model

Introduction:
The development of a text detection and font recognition model involves several steps, including text detection, font recognition, and model integration. This report details the approach taken to develop the model using various algorithms and technologies.

1. Text Detection:
Text detection is the process of locating and identifying text regions within an image. In this implementation, EasyOCR, a Python library for optical character recognition, is utilized for text detection. EasyOCR provides a straightforward interface for detecting text in images. The following steps are involved in text detection:

- Import Libraries: The necessary libraries are imported, including OpenCV (cv2) for image processing, EasyOCR for text detection, Matplotlib for visualization, NumPy for numerical operations, and TensorFlow for loading the font recognition model.
- Read Image: The target image is read using OpenCV's `cv2.imread` function.
- Text Detection: EasyOCR's `Reader` class is used to perform text detection on the image. The `readtext` method detects text regions along with bounding boxes and confidence scores.
- Thresholding: A threshold is applied to filter out text regions with low confidence scores.

2. Font Recognition:
Font recognition involves identifying the font style of text regions detected in the image. This is accomplished using a pre-trained deep learning model. The steps for font recognition are as follows:

- Preprocess Image Patch: The text patch extracted from the image is preprocessed to match the input requirements of the font recognition model using resizing to 64 x 64 and normalization by dividing by 255 as each image has values between 0 to 255. This includes converting the patch to grayscale, resizing it to a fixed size, and normalizing pixel values.
- Predict Font: The preprocessed image patch is passed through the font recognition model to predict the font style. The model outputs class probabilities, from which the predicted font class is determined.

3. Evaluation: Evaluated model using accuracy metrics and got 98.5 % accuracy.
  
4. Model Integration and Visualization:
The text detection and font recognition components are integrated to annotate the image with detected text regions and predicted font styles. The annotated image is visualized using Matplotlib.

Technologies Used:
- OpenCV (cv2): Used for image processing tasks such as reading images and drawing bounding boxes.
- EasyOCR: Employed for text detection, providing an efficient solution for detecting text regions in images.
- Matplotlib: Utilized for visualizing the annotated image with text regions and predicted fonts.
- NumPy: Used for numerical operations and array manipulation.
- TensorFlow: Employed for loading the pre-trained font recognition model and making predictions.

Conclusion:
The developed text detection and font recognition model successfully identifies text regions in images and predicts the font style of the detected text. This model can be further enhanced and integrated into various applications requiring automated text analysis and font recognition capabilities.

Recommendations for Future Work:
- We can also train our model on color font detection which will also recognizing the color used in font, which will helpful during the maintenance of the aircraft, filling and recognizing the maintenance reports and spare parts box texts recognitions.

- By increasing epochs, the model accuracy can increase. Also we can introduce cache and prefetch to reduce the training period.
![image](https://github.com/Rohit-Saswadkar/Font-Text-classification-project-using-CNN/assets/126965510/d035db70-44a3-463f-a921-93861eee7c7c)


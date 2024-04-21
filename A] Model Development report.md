Presentation - https://docs.google.com/presentation/d/1JGPd1MOcGTFJOqq3h9TaKggLBuI0Nyak/edit?usp=sharing&ouid=115169350078482455358&rtpof=true&sd=true
Approach I taken for our project:
1. Data Collection:
   - There is a dataset available for font detection on kaggel having 2 datasets init as Font Dataset Large and Font Dataset Large Color, containing 48 different font types each.
   - I Chose the Font Dataset Large due to hardware constraints and time constraints for data uploading on Google Drive.

2. Data Preprocessing:
I Created a function as load data and did this tasks - 
   - Loaded the dataset and separated font labels and images using a custom function.
   - Converted the images to grayscale using OpenCV (cv2) as the model was trained on a laptop, hence reducing computational load.
   - Resized the images to 64x64 pixels to maintain uniformity and also reduces computational load on laptop.

3. Data Splitting:
   - Split the dataset into training, validation, and test sets using the train_test_split function from scikit-learn. 
   - Also I applied one hot encoding on labels.  
   - Shuffled the data while splitting as it improves the model generalization on different labels.
   - before training we should have to normalize the pixel values to the range [0, 1] by dividing each pixel value by 255.
   - So I applied normalization to the training, validation, and test sets

4. Model Architecture:
   - I Built a Convolutional Neural Network (CNN) model using the sequential API from TensorFlow Keras.
   - Created a CNN layer with 32 filters of size 3x3 and ReLU activation function, followed by a MaxPooling2D layer with a 2x2 window size to extract low-level features efficiently. 
   - I chose the filters size as 32 as it reduces computational load. But we can also increase the filter size to improve the model accuracy 
   - Added another CNN layer with 64 filters to capture more complex data and ReLU activation, followed by MaxPooling2D, to capture higher-level features in the data.
   - Added a third CNN layer with 64 filters and ReLU activation, followed by MaxPooling2D, for further feature extraction and abstraction.
   - Flattened the output and added a Dense layer with 64 neurons and ReLU activation to introduce non-linearity and increase model complexity.
   - Added the output layer with softmax activation to predict the font classes, converting raw outputs into class probabilities.

5. Model Compilation and Training:
   - I Compiled the model using categorical cross entropy loss as our labels has binary values after applying one hot encoding and the Adam optimizer as learning rate because of its robust performance during training.
   - Trained the model on the training data for 10 epochs with a batch size of 32.
   - Validated the model on the validation set during training.

6. Model Evaluation:
   - I evaluated the trained model on the validation and test datasets to get its accuracy and understand its performance using accuracy metric as it well suitable for classification tasks.
   - Achieved high accuracies on all datasets: 99.19% on the training set, 99.23% on the validation set, and 99.23% on the test set.
- Also I input the test image and predicted its class accurately.

7. Model Saving:
   - Saved the trained model for future use.

Overall, the developed font detection model demonstrated excellent performance with high accuracy, effectively distinguishing between different font types. The model architecture leverages convolutional layers for feature extraction and a dense layer for classification, resulting in robust font detection capabilities.

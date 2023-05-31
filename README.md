# SUMMER_PROJECT
Real time Driver Drowsiness detection system
STEP-1 Libraries
I have imported all the necessary libraries: tenserflow, cv2,os, pickle,numpy,patool
STEP-2 Downloaded the dataset: Drowsiness Detection Dataset | Kaggle
Step 3: Importing and preprocessing the data
At start we initialize the classes and folder. 
Now for each folder in train  (i.e. open_eyes and closed_eyes) we append it to the train_data list. Before appending we also resize images to 224x224 as our model architecture will require inputs of 224x224 size.
Next we will shuffle our data 
After that, group the data into x & y. So x will be storing the images and y will have their category (closed_eye or open_eye)
The shape of x. It should be (No. of images(4000),224,224,3).Image dimension (3 bcoz it’ll be RGB image)
Now Normalize the data in x:(make all data points b/w 0&1) to generalise the data.
We will also convert y to a numpy array like we did with x.
After that save your variables
Step 4: Understanding the model architecture 
We will be using the mobileNet model and performing transfer learning on it. We use it as it is a lightweight model and since we will be deploying our model, it is better to have a lightweight model.
Step 5: Building the model
We will first load the mobileNet model from keras
Get the summary about the model and its different layers
Then we perform transefer learning
Next, we compile our model
Now we will train our model
Step 6: Checking the network for predictions on eye images
Let us first make predictions  on simple images of eyes that to test. you will see that predection on open eyes will be negative value and closed eyes will be positive value.
Step 7: Detecting eyes from face and applying our model on it for prediction
For detecting eyes,we will be using the haarcascade model for eye detection. Then we will crop the eyes and apply our model to make predictions.
Let us first load the image
Next, get the haarcascade files for face and eye detection
Then, we will convert it to grayscale bcoz we trained our model on grayscale images.
Next we detect the eyes and draw rectangles around the eyes. Sometimes the haarcascade detects nose holes or anything in the background as eyes, so we slice the array to include 2 elements(2 eyes).
Next,we will crop the eye 
We now perform similar operations on the eye image that we did earlier on gray image (in step 6)
Let us see the prediction,  its -ve i.e. it is open eye. 










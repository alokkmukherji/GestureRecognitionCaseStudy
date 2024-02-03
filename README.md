# Gesture Recognition Case study 

 By Aloke Kumar Mukherjee (alokkmukherjee@gmail.com)


### Problem Statement
To develop a cool feature in the smart-TV that can recognise five different gestures performed by the user which will help users control the TV without using a remote.

The gestures are continuously monitored by the webcam mounted on the TV. Each gesture corresponds to a specific command:

* Thumbs up: Increase the volume
* Thumbs down: Decrease the volume
* Left swipe: 'Jump' backwards 10 seconds
* Right swipe: 'Jump' forward 10 seconds
* Stop: Pause the movie

### Understanding the Dataset
* The training data consists of a few hundred videos categorised into one of the five classes.
* Each video (typically 2-3 seconds long) is divided into a sequence of 30 frames(images).
* These videos have been recorded by various people performing one of the five gestures in front of a webcam - similar to 
  what the smart TV will use.
* The data is in a zip file. The zip file contains a 'train' and a 'val' folder with two CSV files for the two folders. 
  These folders are in turn divided into subfolders where each subfolder represents a video of a particular gesture. Each 
  subfolder, i.e. a video, contains 30 frames (or images).
* All images in a particular video subfolder have the same dimensions but different videos may have different dimensions. 
  Specifically, videos have two types* of dimensions - either 360x360 or 120x160 (depending on the webcam used to record the 
  videos). So some pre-processing is required to standardise the videos.
* Each row of the CSV file represents one video and contains three main pieces of information - the name of the subfolder 
  containing the 30 images of the video, the name of the gesture and the numeric label (between 0-4) of the video.

 ### Goal

The task is to train a model on the 'train' folder which performs well on the 'val' folder as well (as usually done in ML projects). There is the test folder for evaluation purposes - the final model's performance will be tested on the 'test' set.

### Model Training
* Used CONV3D Arch
* Experimented with different model configurations, hyper-parameters, various iterations and combinations of batch sizes, image dimensions, etc.
* Used Adam () as it led to improvement in model’s accuracy by rectifying high variance in the model’s parameters. 
* Used Batch Normalization, pooling and dropout layers when our model started to overfit.

### Data Generator / Model Class
Created a Model Class which will perform the following:
 * All the initialisations of paths, image properties and model properties
 *	Generator function for generating the data with labels
     * The images will be cropped to the size we want
     * The images with irregular dimension will be centre cropped on the x-axis equally on both sides
     * We save the model only when the validation loss decreases
     * Learning rate decreases when approaching the minima
 * A generic train functions.
 * Plotting the model
 * An abstract method to define our own model by inheriting this class


### Result Summary
The model 3 is showing the best performance and so it has been considered as final model

![image](https://github.com/alokkmukherji/GestureRecognitionCaseStudy/assets/140543380/232d845a-7318-40f6-9fb7-16aaac47ff11)


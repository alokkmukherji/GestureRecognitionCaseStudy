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

### Objectives:
1. **Generator**:  The generator should be able to take a batch of videos as input without any error. Steps like cropping, resizing and normalization should be performed successfully.

2. **Model**: Develop a model that is able to train without any errors which will be judged on the total number of parameters (as the inference(prediction) time should be less) and the accuracy achieved. As suggested by Snehansu, start training on a small amount of data and then proceed further.

3. **Write up**: This should contain the detailed procedure followed in choosing the final model. The write up should start with the reason for choosing the base model, then highlight the reasons and metrics taken into consideration to modify and experiment to arrive at the final model.


### Results:

![observations](https://user-images.githubusercontent.com/29462447/86066095-d501aa80-ba8e-11ea-82d8-4681e20e310e.png)

I choose CNN+LSTM based model as the final choice due to fairly decent accuracy considering the type of data as well the no. of parameters as I wanted my model to be light weight in nature.


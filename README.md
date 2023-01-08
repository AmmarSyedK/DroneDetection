![TensorFlow - Logo](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiRgwmbW2Tp7Q_Y3GTKSmkfboFNHuUizDaYh1uLrQSCZarfkvs1mK7OodevH9l318Ls8ddEmKNPewlpVhMJzKvtpktP6TeKniEEMAzgRrHq-D-kIEsoQnZyvc7n4pUVsn1RkFF066dnujQZ1htprWST0uSJftVZxQyc2Qm8aijQTMhrtJlj7rrEc6s7/s1600/Tensorflow-septmber-update-header%20%282%29.png)
# TensorFlow - Drone Detection


This is a drone detection program usable for both images or videos (real time or pre-recorded video). It was made using TensorFlow 1 and it heavily relies on sentdex's tutorial on YouTube. There is a new version of TensorFlow now (TF2) so this program is deprecated.

# Information

In order to have an object detection program, we need to train our model. This model has been trained using 100 `test/` images of drones and over 500 `train/` images which is quite low to train a model but it is a good start.

Once we have gathered all the images, we need to actually train the model. For that, we can use `TensorFlow-gpu` which will use our computer GPU to train our model OR we can use `Google Colab` to train our model which is way more faster.

Google Colab allows us to execute arbitrary python code through the browser, and is especially well suited to machine learning, data analysis and education. 
To execute the code faster, Google Colab has been used, you can find the model in `DroneDetection/ModelTrainingOnColab.ipynb`.

After training the model, we can finally test it out on an image or a video. For this project I have tried to gather some video clips and test it out. Here are the result:

https://user-images.githubusercontent.com/76450681/211209661-be069c27-5e96-4651-a448-fdc2bcbb9d3d.mp4

We can see that it recognize the drones quite accuratly.

# Requirements

- You must have Python 3.7 installed on your computer, TensorFlow 1.15 can not be downloaded using a more recent version than 3.7
- This program was tested using TensorFlow 1.15, I recommend trying it using this version
- You need to install protoc 3.4 in order for this program to work. No other version than this one will work. You can find the download link [here](https://github.com/protocolbuffers/protobuf/releases/tag/v3.4.0)


# Installation

Before talking about the installation, the program is outdated so it might be hard to make it working today. We need to install the old version of Python (3.7), Tensorflow (1.15) and Protoc (3.4). I don't know if it still works.

Here are the steps to launch the program:

- From `DroneDetection/` folder and run the following command:
```sh
protoc object_detection/protos/*.proto --python_out=.
```
- Edit the `custom_model.py` from the `DroneDetection/drone_detection` folder to choose the video or image you want to test.
At the line 21:
```sh
cap  =  cv2.imread([PATH/TO/VIDEO/IMAGE])
```
- If you want to test it on your webcam, you can use:
```sh
cap  =  cv2.VideoCapture(0)
```
After following this steps, the webcam, the image or the video should be showing on your command prompt and every drone will be detected if accurate.
# Credits

- Thanks to TensorFlow
- Thanks to Google Colab
- Thanks to sentdex's YouTube video [tutorial](https://youtube.com/playlist?list=PLQVvvaa0QuDcNK5GeCQnxYnSSaar2tpku)

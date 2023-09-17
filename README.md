# **Pose Estimation on BrainyPi**

This repo is a fork of ecd1012/rpi_pose_estimation. I have changed it to make it compatible on a BrainyPi by removing all GPIO triggered functions

Results
=======
<img src="images/pose.gif" width="500" height="500">

Description of Repository
=========================
This repository contains code and instructions to configure the necessary software for running pose estimation on BrainyPi!

Details of Software and Neural Network Model for Object Detection:
* Language: Python
* Framework: TensorFlow Lite
* Network: PoseNet with MobileNet-V1

Additional Resources
===================
* **Blog Post on Posenet**: https://medium.com/tensorflow/real-time-human-pose-estimation-in-the-browser-with-tensorflow-js-7dd0bc881cd5
* **Blog Post on this project**: https://ecd1012.medium.com/pose-estimation-on-the-raspberry-pi-4-83a02164eb8e
* **Pose estimation with TensorFlow Lite**:https://www.tensorflow.org/lite/models/pose_estimation/overview

Setting Up Software
====================
1.) Clone Repository:
```
git clone https://github.com/RakhulKumar/Pose-Estimation-in-BrainyPi-using-TFLite.git
````
2.) Change directory to source code:
```
cd Pose-Estimation-in-BrainyPi-using-TFLite
```
3.) Please see my other post here: https://github.com/ecd1012/rpi_road_object_detection
And follow **Setting Up Software** Steps: 3-9 before proceeding
Here is a video of those steps: https://youtu.be/Zfmo3bMycUg

4.)At this point, you should have all the dependencies installed and your virtual environment activated.

5.) Grab the sample TensorFlow Lite Posenet model from Google
```
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/posenet_mobilenet_v1_100_257x257_multi_kpt_stripped.tflite
```

Setting Up Virtual Environment
===================
1.) Open command prompt and make sure pi is up to date:
```
sudo apt-get update && sudo apt-get upgrade
```
2.) Install virtual environment: 
```
sudo pip3 install virtualenv
```
3.) Make virtual environment:
```
python3.7 -m venv TFLite-venv
```
4.) Activate Environment:
```
source TFLite-venv/bin/activate
```
5.) Install the dependencies:
```
bash get_py_requirements.sh

```

Running Pose Estimation
=================
1.) After all your software is configured correctly run the following command:
```
python3 run_pose_estimation.py --modeldir posenet_mobilenet_v1_100_257x257_multi_kpt_stripped.tflite --output_path save_img
```
Where the --output_path you specify is where you want images saved.

2.) The script will start running and the processed images will be saved to the '--output_path' you specified over the command line, with a timestamped name for each frame.



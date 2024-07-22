# Object Detection using Detectnet

Detectnet is a neural network designed for object detection tasks. 
We will be evaluating the detectnet for this module and make changes to optimize it to the model city over the next modules. 

## Installation

Firstly for setting up the environment, Clone the detectnet for ros2

```
    git clone https://github.com/dusty-nv/ros_deep_learning.git
```

Next, build and source the files

```
    colcon build
    source install/setup.bash
```

Note that the realsense camera must be running for using the detectnet. 
For launching the IntelRealSense Camera

```
    ros2 launch realsense2_camera rs_launch.py
```

Configure the launch files for the output of the camera '/camera/color/image_raw'
For launching detectnet

```
    ros2 launch ros_deep_learning detectnet.ros2.launch
```

## Evaluation 

Evaluation of the detectnet model is required to see how effective it is at distinguising the different objects. We need to know the accuracy of the model to know how much we can depend on the system.

The image below shows the object detection in action. We can see that the car on the right side is detected with a confidence of 78.2%. The car on the left side is not detected. The person is also detected but with a confidence of 79.7%. The confidence can be improved along with the detection (the left car is not detected).

<div align="center">
    <img src="images/Detection_image_1.png" width=900 height=500>
</div>

The image below shows the confidence on the detection of the person has improved to 95.9% as the person got closer to the vehicle. The car detection has also slightly increased to 80.5% confidence without any changes made to the car or the distance to the car.

<div align="center">
    <img src="images/Detection_image_2.png" width=900 height=500>
</div>

The image below shows the left car being labelled as a motorcycle with a confidence of 56.5%. The detection can still be improved. 

<div align="center">
    <img src="images/Detection_image_3.png" width=900 height=500>
</div>

In the image below, we can see the traffic light is not detected. The detection of the traffic light also would benefit the project in the future.

<div align="center">
    <img src="images/Detection_image_4.png" width=900 height=500>
</div>

In the image below, we can see that the potted plant obstacle is recognized when kept in the centre of the camera view. Initially the pot was on the side, but it was not recognized. It seems that the obstacles far away are not recognized efficiently. 

<div align="center">
    <img src="images/Detection_image_5.png" width=900 height=500>
</div>

In the image below, a cardboard board is recognized as a TV. Even though that recognition is not needed to be rectified for our implementation, the team can try to improve on the object detection. 

<div align="center">
    <img src="images/Detection_image_6.png" width=900 height=500>
</div>

The evaluation of the detectnet model shows varying accuracy in object detection, with some objects like cars and persons detected with moderate confidence, while others, like traffic lights and distant obstacles, are often missed or misclassified. Improvements are needed to enhance detection accuracy and reliability, especially for critical objects like traffic lights and vehicles. Future work should focus on addressing these detection inconsistencies.

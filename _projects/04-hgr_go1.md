---
name: Gesture-Based Quadruped Control
tools: [ROS2, Python, C++, Quadruped, Computer Vision, MediaPipe]
image: https://avazahedi.github.io/assets/go1.gif
description: Controlling the Unitree Go1 quadruped robot via hand gestures.
---

# Gesture-Based Quadruped Control

## **Description**
In this project, I developed software that uses hand gestures to send motion commands to the Unitree Go1 robot dog.  
The go1-gesture-command repository consists of two ROS2 packages, one Python and one C++. 

<div style="position: relative; padding-bottom: 31.95%; height:0; overflow: hidden;">
    <center><video src="https://user-images.githubusercontent.com/39091881/226089569-d1528114-414c-4960-8ec3-f1f7acc11ab2.mp4" controls style="position: absolute; top:0; left:0; width: 100%; height: 100%;"></video></center>
</div>

<br>

## **Packages**
* The ros2_hgr package includes nodes for hand gesture recognition and sending commands to the Unitree Go1 robot dog.  

* The go1_cmd package includes a node for receiving gesture data and converting them to movement commands for the Go1.

<br>

## **How It Works**

### Project Flowchart
<br>
<center><img src="{{ site.url }}{{ site.baseurl }}/assets/go1_flowchart.jpg"/></center>
<br>


### Hand Gesture Recognition

<div style="position: relative; padding-bottom: 100%; height:0; overflow: hidden;">
    <center><video src="https://user-images.githubusercontent.com/39091881/226089470-37c993d5-ed02-45c1-83af-3d6137bb76a5.mp4" controls style="position: absolute; top:0; left:0; width: 100%; height: 100%;"></video></center>
</div>

<br>

#### Gestures Guide
<ol start="0">
  <li>Open - stop</li>
  <li>Close - look forward (normal 0&deg; yaw)</li>
  <li>Pointer - recover stand up</li>
  <li>OK - look up</li>
  <li>Peace - look down</li>
  <li>Thumbs Up - walk forward</li>
  <li>Thumbs Down - walk backward</li>
  <li>Quiet Coyote - lay down</li>
</ol>

<br>
I forked a repository from GitHub user Kinivi that includes a program and TensorFlow model for using MediaPipe to detect and label hand gestures. In my ros2_hgr package, I transformed their code into a ROS2 Python package that can publish data through a node. I also added new gestures (gestures 4-7) and retrained the model with new data for both the existing gestures and the new ones.  
<br>
<br>

#### MediaPipe Hand Landmarks

Here, MediaPipe works by detecting 21 points throughout a hand. The model I use in this project identifies the locations of each of these points and, based on their overall configuration, labels the gesture. 

<br>
<br>
<center><img src="{{ site.url }}{{ site.baseurl }}/assets/hand_landmarks.png"/></center>
<br>
<br>

### Commanding the Go1

In another node, I receive the hand gesture labels and use them to send out a variety of commands to the Go1, employing the unitree_ros2 and unitree_nav packages mentioned in the prerequisites section.  
The following video shows some movements that come pre-programmed and can be controlled via the provided remote control.  

<div style="position: relative; padding-bottom: 56.25%; height:0; overflow: hidden;">
    <center><video src="https://user-images.githubusercontent.com/39091881/226089749-09f4dedc-a96d-4bd7-ac2e-195d2e96af29.mp4" controls style="position: absolute; top:0; left:0; width: 100%; height: 100%;"></video></center>
</div>

<br>
<br>

### About the Unitree Go1
The Unitree Go1 is a quadruped robot advertised for its high dynamics, intelligence, and companionship abilities.  

<br>
<center><img src="{{ site.url }}{{ site.baseurl }}/assets/go1_dancing.gif"/></center>
<br>

### Notes
A large part of getting the Go1 up and running with Ubuntu 22.04 and ros2-humble consisted of the disassembly and updates performed as a group with other students with projects involving the Go1: Marno Nel, Nick Morales, and Katie Hughes.  

<br>
<a href="https://github.com/avazahedi/go1-gesture-command">go1-gesture-command GitHub Repository</a>

---
name: Gesture-Based Quadruped Control
tools: [ROS2, Python, C++, Quadruped, Computer Vision, MediaPipe]
image: https://avazahedi.github.io/assets/go1.gif
description: Controlling the Unitree Go1 quadruped robot via hand gestures.
---

# Gesture-Based Quadruped Control
<br>

### **Description**
In this project, I developed software for using hand gestures to send motion commands to the Unitree Go1 robot dog.  
The go1-gesture-command repository consists of two ROS2 packages, one Python and one C++. 

<center>
</center>

### **Packages**
* The ros2_hgr package includes nodes for hand gesture recognition and sending commands to the Unitree Go1 robot dog.
* The go1_cmd packages includes a node for receiving gesture data and converting them to movement commands for the Go1.

<br>
<br>

### **How It Works**

Project Flowchart


#### Hand Gesture Recognition
<br>

<!-- <center><video width="270" height="480" controls>
  <source src="https://user-images.githubusercontent.com/39091881/206932493-6110ad55-7bdc-4c57-898e-caeab954bc97.mp4">
</video></center>  -->

<center>
</center>

<br>
I forked a repository from GitHub user Kinivi that includes a program and TensorFlow model for using MediaPipe to detect and label hand gestures. In my ros2_hgr package, I transformed their code into a ROS2 Python package that can publish data through a node. I also added new gestures and retrained the model with new data.
<br>
<br>

#### Commanding the Go1
<br>

<!-- <center><video width="270" height="480" controls>
  <source src="https://user-images.githubusercontent.com/39091881/206932493-6110ad55-7bdc-4c57-898e-caeab954bc97.mp4">
</video></center>  -->

<center>
</center>

<br>
In another node, I receive the hand gesture labels and use them to send out a variety of commands to the Go1, employing the unitree_ros2 and unitree_nav packages mentioned in the prerequisites section.
<br>
<br>

#### Putting It All Together
<br>

<!-- <center><video width="270" height="480" controls>
  <source src="https://user-images.githubusercontent.com/39091881/206932493-6110ad55-7bdc-4c57-898e-caeab954bc97.mp4">
</video></center>  -->

<center>
</center>

<br>
<br>

#### More About the Unitree Go1
The Unitree Go1 is a quadruped robot advertised for its high dynamics, intelligence, and companionship abilities. The following video shows some movements that come pre-programmed and can be controlled via the provided remote control.  

<!-- <center><video width="270" height="480" controls>
  <source src="https://user-images.githubusercontent.com/39091881/206932493-6110ad55-7bdc-4c57-898e-caeab954bc97.mp4">
</video></center>  -->

<center>
</center>

<br>

#### Notes
A large part of getting the Go1 up and running with Ubuntu 22.04 and ros2-humble consisted of the disassembly and updates performed as a group with other students with projects involving the Go1: Marno Nel, Nick Morales, and Katie Hughes.  

<br>
<a href="https://github.com/avazahedi/go1-gesture-command">go1-gesture-command GitHub Repository</a>

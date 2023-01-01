---
name: Pen Challenge
tools: [Python, OpenCV, ROS2]
image: https://avazahedi.github.io/assets/hackathon-pen-challenge-snapshot.png
description: Using computer vision to grasp a pen.
---

## Pen Challenge

As part of Northwestern's MSR orientation, we did a 2-week hackathon to develop our skills in Python, Linux, and Git.  

One particularly fun project was programming the PincherX 100 desktop robot arm to grasp a pen and return it to a home position. Controlling the arm was done with Python and the Interbotix ROS packages. For detecting the pen, we used OpenCV and RealSense cameras to detect the pen by color, calculate its location relative to the base of the robot, and send desired end-effector coordinates to the robot for movement.  

<br>
<center><video width="270" height="480" controls>
  <source src="{{ site.url }}{{ site.baseurl }}/assets/hackathon-pen-challenge-video-1.mp4">
</video></center> 
<br>


<!-- <p align="middle"> -->
<p float="left">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/hackathon-pen-challenge-snapshot.png" width="20%" />
  <img src="{{ site.url }}{{ site.baseurl }}/assets/hackathon-pen-challenge-snapshot2.png" width="20%" /> 
</p>

<a href="https://github.com/avazahedi/pen-challenge">Pen Challenge GitHub Repository</a>
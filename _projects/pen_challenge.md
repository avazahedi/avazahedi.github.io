---
name: Pen Challenge
tools: [Python, Linux, Git, OpenCV, ROS2, Embedded Systems]
image:
description: Using computer vision to grasp a pen.
---

## Pen Challenge

As part of Northwestern's MSR orientation, we did a 2-week hackathon to develop our skills in Python, Linux, and Git.  

One particularly fun project was programming the PincherX 100 desktop robot arm to grasp a pen and return it to a home position. Controlling the arm was done with Python and the Interbotix ROS packages. For detecting the pen, we used OpenCV and RealSense cameras to detect the pen by color, calculate its location relative to the base of the robot, and send desired end-effector coordinates to the robot for movement.  

GitHub: https://github.com/avazahedi/pen-challenge
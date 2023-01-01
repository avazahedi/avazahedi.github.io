---
name: Pen Challenge
tools: [Python, OpenCV, ROS2]
image:
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


<!-- <p float="left">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/hackathon-pen-challenge-snapshot.png" width="48%" />
  <img src="{{ site.url }}{{ site.baseurl }}/assets/hackathon-pen-challenge-snapshot2.png" width="48%" /> 
  <!-- <img src="{{ site.url }}{{ site.baseurl }}/assets/cloudbot_poster.jpg" width="32%" /> -->
</p> -->

<p align="middle">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/hackathon-pen-challenge-snapshot.png" width="48%" />
  <img src="{{ site.url }}{{ site.baseurl }}/assets/hackathon-pen-challenge-snapshot2.png" width="48%" /> 
  <!-- <img src="{{ site.url }}{{ site.baseurl }}/assets/cloudbot_poster.jpg" width="32%" /> -->
</p>

<!-- <center><iframe width="1193" height="671" src="https://www.youtube.com/embed/ePDHq-Qqdfw" title="Hackathon Pen Challenge 1" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></center> -->

<a href="https://github.com/avazahedi/pen-challenge">Pen Challenge GitHub Repository</a>
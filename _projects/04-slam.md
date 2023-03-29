---
name: TurtleBot3 Simulation, Control, and SLAM
tools: [ROS2, C++, Simulation, SLAM]
image: https://avazahedi.github.io/assets/slam.gif
description: Simulation, control, and EKF SLAM packages for the TurtleBot3 using ROS2 in C++.
---

# TurtleBot3 Simulation, Control, and SLAM

## **Description**
This project was done throughout the winter quarter and includes 4 packages for NU TurtleBot visualization, simulation, control, and SLAM.  

<!-- <center><video width="845" height="270" controls>
  <source src="https://user-images.githubusercontent.com/39091881/226089569-d1528114-414c-4960-8ec3-f1f7acc11ab2.mp4">
</video></center>  -->

<br>

## **Packages**
* nuturtle_description
    * This package contains urdf files and basic debugging, testing, and visualization code for the WI2023 ME 495 robots.
* nusim
    * This package provides a simulated robot environment and uses rviz2 for visualization for a red NU turtlebot.
* nuturtle_control 
    * This package enables control of the turtlebot via messages on the cmd_vel topic.
* nuslam
    * This package allows the turtlebot to perform SLAM with an Extended Kalman Filter implementation.

<br>

### RQT Graph
<br>
<center><img src="{{ site.url }}{{ site.baseurl }}/assets/slam_rqt_graph.png"/></center>
<br>


### Live Demo

Teleoperating the TurtleBot via cmd_vel messages. In this demo, the TurtleBot is commanded to move in a circle.  

<center><video width="480" height="480" controls>
  <source src="https://user-images.githubusercontent.com/39091881/226089470-37c993d5-ed02-45c1-83af-3d6137bb76a5.mp4">
</video></center> 

<br>

### Simulation Demo w/ SLAM

Moving around obstacles and using SLAM to correct the position estimate of the TurtleBot.  

<center><video width="480" height="480" controls>
  <source src="https://user-images.githubusercontent.com/39091881/226089470-37c993d5-ed02-45c1-83af-3d6137bb76a5.mp4">
</video></center> 

<br>

<br>
<a href="https://github.com/avazahedi/nuturtlebot-slam">nuturtlebot-slam GitHub Repository</a>

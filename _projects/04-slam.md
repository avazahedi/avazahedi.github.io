---
name: TurtleBot3 Simulation, Control, and SLAM
tools: [ROS2, C++, Simulation, SLAM]
image: https://avazahedi.github.io/assets/slam.gif
description: Simulation, control, and EKF SLAM packages for the TurtleBot3 using ROS2 in C++.
---

# TurtleBot3 Simulation, Control, and SLAM

## **Description**
This project was done throughout the winter quarter and includes 4 packages for NU TurtleBot visualization, simulation, control, and SLAM.  

<br>

### Live Demo

Teleoperating the TurtleBot via cmd_vel messages. In this demo, the TurtleBot is commanded to move in a circle.  

<center><video width="1280" height="720" controls>
  <source src="https://user-images.githubusercontent.com/39091881/228632617-749a7fd4-b361-4821-a335-1c61dcb1b71d.mp4">
</video></center> 

<br>

### Simulation Demo w/ SLAM

Moving around obstacles and using SLAM to correct the position estimate of the TurtleBot.  

<center><video width="1280" height="720" controls>
  <source src="https://user-images.githubusercontent.com/39091881/228632783-821439fa-0247-4cff-8bf6-4dd80112a653.webm">
</video></center> 

<br>

* Red: actual robot position  
* Blue: robot position based on odometry  
* Green: robot position estimate based on SLAM  

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

<br>
<a href="https://github.com/avazahedi/nuturtlebot-slam">nuturtlebot-slam GitHub Repository</a>

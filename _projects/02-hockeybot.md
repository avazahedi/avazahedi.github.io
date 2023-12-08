---
name: HockeyBot
tools: [Python, ROS2, OpenCV, Embedded Systems]
image: https://avazahedi.github.io/assets/hockeybot.gif
description: ROS2 package allowing a Franka Emika arm to play air hockey.
---

# HockeyBot
<br>

### **Description**
The HockeyBot package allows a Franka robot to play air hockey. We use a RealSense camera and computer vision to detect where the puck is on the air hockey table. Our TrajCalc node predicts the trajectory of the puck and sends those positions to our SimpleMove API, which tells the Franka to move to meet the puck. All of these tasks are integrated in our Main node, which completes our workflow and allows the robot to play repeatedly.  

In this project, my main focus was on robot control and integration. I worked closely with one of my group members, Marno Nel, to set up service calls for moving the Franka to key points as well as overall flow. Additionally, I developed the Main node, which connects all other nodes and was essential to allowing the robot to play. I also created the start-up sequence and included error handling.  

HockeyBot Group Members: Ava Zahedi, Marno Nel, Ritika Ghosh, Hanyin Yuan  
<br>
<br>

### **Overall System Architecture**

#### Start-Up Sequence
<br>

<center><video width="270" height="480" controls>
  <source src="https://user-images.githubusercontent.com/39091881/206932493-6110ad55-7bdc-4c57-898e-caeab954bc97.mp4">
</video></center> 

<br>
* Upon launch, the robot follows a start-up sequence to reach its home position. It does this by following a series of waypoints 
to smoothly reach its goal. The start-up sequence also allows for flexibility in grasping the paddle to avoid excessive force during 
gameplay. This was one of my tasks in this project.
<br>
<br>


#### Computer Vision
<br>

<center><video width="480" height="270" controls>
  <source src="https://user-images.githubusercontent.com/60977336/206880795-9153ac89-7eeb-42bf-a819-3e3e85a09f68.mp4">
</video></center> 

<br>
* A RealSense camera is used alongside computer vision to detect and track puck movement. This portion of the project was the focus of Ritika Ghosh and Hanyin Yuan.
<br>
<br>


#### Trajectory Calculations
<br>

<center><video width="480" height="270" controls>
  <source src="https://user-images.githubusercontent.com/60977336/206880201-e1849e50-2c71-4b56-8993-bf7feea20640.mp4">
</video></center> 

<br>
* From detecting the puck's location via computer vision, the puck's trajectory could be predicted assuming a straight-line path. This enabled the Franka to move along the puck's predicted path to make impact. This portion of the project was done by Marno Nel. 
<br>
<br>


#### Hitting the Puck
<br>

<center><video width="480" height="270" controls>
  <source src="https://user-images.githubusercontent.com/60728026/206883262-3a7bd3e8-8259-4f35-b5ad-2bc805d5e52b.mp4">
</video></center>

<br>
* After receiving waypoint and goal positions, the robot receives service calls to move to those points, thereby meeting 
the puck along its trajectory and hitting it. If there is an edge case where the robot cannot successfully meet the puck 
given its trajectory, the robot will block instead.
<br>
<br>


#### Return Home
* As the robot is moving to hit the puck, it also plans a path from where it hits the puck back to the home position. 
Once the robot detects that its end-effector has reached the goal, it begins executing the path back home. This process 
also resets all internal variables and restarts the loop so that the robot can continue playing.

<br>
<a href="https://github.com/avazahedi/HockeyBot">HockeyBot GitHub Repository</a>
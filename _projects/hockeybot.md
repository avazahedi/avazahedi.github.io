---
name: HockeyBot
tools: [Python, ROS2, OpenCV, Embedded Systems]
image: https://www.sketchappsources.com/resources/source-image/project-neon-groove-music-ui.png
description: ROS2 package allowing a Franka Emika arm to play air hockey.
---

## **Description**
The HockeyBot package allows a Franka robot to play air hockey. We use a RealSense camera and computer vision to detect where the puck is on the air hockey table. Our TrajCalc node predicts the trajectory of the puck and sends those positions to our SimpleMove API, which tells the Franka to move to meet the puck. All of these tasks are integrated in our Main node, which completes our workflow and allows the robot to play repeatedly.


## **Overall System Architecture**

### Start-Up Sequence

![preview](https://user-images.githubusercontent.com/39091881/206932493-6110ad55-7bdc-4c57-898e-caeab954bc97.mp4)

* Upon launch, the robot follows a start-up sequence to reach its home position. The robot follows a series of waypoints 
to reach the home x- and y-coordinates with an offset in the z. It then reaches down to grasp the adapter on the paddle 
and moves back up slightly. This slight increase in height allows the robot flexibility while moving, so that if it pushes 
down during movement, it will not apply a force into the table while still keeping the paddle level with the table.


### Computer Vision

![preview](https://user-images.githubusercontent.com/60977336/206880795-9153ac89-7eeb-42bf-a819-3e3e85a09f68.mp4)


* Intel RealSense D435i is used at 480x270x90 allowing the puck to be tracked at 90 fps. As soon as the streaming has been enabled, this node detects the center of the table in pixel coordinates. Then with the help of the depth camera, the deproject function is used to convert pixel coordinates into real world coordinates with respect to the camera. Since the distance between the air hockey table and the Franka robot is known, points from the camera's frame of reference can be transformed to the robot's frame of reference. Next, with the help of OpenCV's HughCircles function the center of the puck is tracked in real time. For the calculation of the trajectory, the puck is only tracked when going towards the robot and up to the center of the table. In order to get rid of noise, before publishing the puck's position it is checked whether the point is close (with a prefixed tolerance) to the best fit line of the previous positions obtained. Note: The output video shows the tracked puck encircled with a black border, regardless of whether all these points are published (in other words, the video shows the contour for every direction of movement of the puck).


### Trajectory Calculations

![preview](https://user-images.githubusercontent.com/60977336/206880201-e1849e50-2c71-4b56-8993-bf7feea20640.mp4)

* Calculates the predicted trajectory of the puck and the play waypoints for the robot by using two 
puck coordinates from computer vision. The node handles collisions by reflecting the impact angle about the normal line. The waypoints for the robot to hit the puck are constrained by the robot's workspace on the air hockey table. The most optimal waypoints are selected by considering all four sides of the robot's workspace. The robot will then move to the first waypoint that is on the predicted trajectory line of the puck and then move along the line to the second waypoint and hit the puck. A plot is dynamically generated and updated each time a new trajectory is calculated. The robot blocks if the trajectory is out of the workspace and unreachable.


### Hitting the Puck

![preview](https://user-images.githubusercontent.com/60728026/206883262-3a7bd3e8-8259-4f35-b5ad-2bc805d5e52b.mp4)

* After receiving waypoint and goal positions, the robot receives service calls to move to those points, thereby meeting 
the puck along its trajectory and hitting it. If there is an edge case where the robot cannot successfully meet the puck 
given its trajectory, the robot will block instead.


### Return Home
* As the robot is moving to hit the puck, it also plans a path from where it hits the puck back to the home position. 
Once the robot detects that its end-effector has reached the goal, it begins executing the path back home. This process 
also resets all internal variables and restarts the loop so that the robot can continue playing.
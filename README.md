# Baxter Robot Raconteur Bridge Workspace Control
Created as part of a project for Robotics I Fall 2017 with Prof. John Wen.

## Description
The script was created to allow for Baxter to be controlled in the workspace using MATLAB running in Windows while taking advantage of the Baxter SDK’s forward and inverse kinematics service. Desired end-effector positions and orientations (represented as a position vector and a quaternion, respectively) can be commanded to the Baxter. Also, the joint positions, joint velocities, joint torques, end-effector positions, end-effector orientations, end-effector twists, and end-effector wrenches are sent to MATLAB. 
## Team Members
Name              | Email           | Github ID
------------------|-----------------|--------------------
Garrison Johnston | johnsg7@rpi.edu | GarrisonJohnston123
Jeffrey Chen      | chenj33@rpi.edu | jeffreychen1018
Stephen Sutton    | suttos2@rpi.edu | stephens18

## Dependancies
### ROS Computer (Tested On [Ubuntu 14.04.5 (Trusty Tahr)]( http://releases.ubuntu.com/14.04/))
1. [Ros Indigo](http://wiki.ros.org/indigo/Installation/Ubuntu) 
2. [The rethink robotics baxter sdk](http://sdk.rethinkrobotics.com/wiki/Main_Page)
3. [Robot Raconteur Python Linux](https://robotraconteur.com/Download?accept=Accept) (You will need to make an account on this site to download)
4. [baxter_rr_bridge]( https://github.com/rpiRobotics/baxter_rr_bridge)
### MATLAB Computer (Tested on Windows 7)
1.  [MATLAB (Tested on 2015a)]( https://www.mathworks.com/products/new_products/release2015a.html)
2. [Robot Raconteur MATLAB Windows](https://robotraconteur.com/Download?accept=Accept) (You will need to make an account on this site to download)
## Instructions
### ROS computer
1. Place workspacecontroller_host.py script in ~/ros_ws/src/baxter_rr_bridge/scripts
2. Navigate into the ros_ws
```
cd ~/ros_ws
```
2.  Run the Baxter shell script
For physical robot:
```
./baxter.sh
```
For simulated robot:
```
./baxter.sh sim
```
3. Start Baxter Gazebo simulator or enable physical robot
For physical robot: 
```
roscore
```
Then in a new terminal window
```
cd ~/ros_ws
./baxter.sh
rosrun baxter_tools enable_robot.py –e
```
For simulated robot:
```
roslaunch baxter_gazebo baxter_world.launch
```
4. In a new terminal window, run
```
rosrun baxter_rr_bridge workspacecontroller_host.py --port <pick 5 digit, unused port number example: 11333> 
```


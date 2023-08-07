# Installation of TurtleBot3 and Performing SLAM with RViz

This guide provides a brief overview of the process to install TurtleBot3 and perform Simultaneous Localization and Mapping (SLAM) using RViz.

To install TurtleBot3, ensure that you have a computer running Ubuntu 18.04 or higher and have ROS Melodic or ROS Noetic installed.

## ROS workspace for TurtleBot3 :

```
$ cd ~/catkin_ws/src
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3_autorace.git
$ cd ..
$ rosdep install --from-paths src -i -y
$ catkin_make
$ source ~/catkin_ws/devel/setup.bash
$ rospack profile
```

## Install Dependent ROS Packages

```
$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
  ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
  ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
  ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
  ros-melodic-rosserial-server ros-melodic-rosserial-client \
  ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
  ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
  ros-melodic-compressed-image-transport ros-melodic-rqt* \
  ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers
```

## Launching TurtleBot3

To start your TurtleBot3, follow these steps:

```
$ echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
$ source ~/.bashrc
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```

![Rivz3](https://github.com/Zahrah794/TurtleBot3/assets/139267881/1bb0e265-f794-4881-9629-6ee00db29c43)



## Starting SLAM with RViz

How to start Simultaneous Localization and Mapping (SLAM) using RViz with your TurtleBot3 robot. SLAM is a powerful technique that enables the robot to create a map of its environment while simultaneously estimating its own position within that map.

```
$ roslaunch turtlebot3_slam turtlebot3_slam.launch
```

![Rivz2](https://github.com/Zahrah794/TurtleBot3/assets/139267881/f5c8762e-47d2-4759-8256-f421aaa76fa1)




## Controlling Robot Movement with Teleoperation Node

How to control the movement of your TurtleBot3 robot using the Teleoperation Node. The Teleoperation Node allows you to send commands from your computer to the robot, enabling you to navigate it remotely.

```
$ rosrun turtlebot3_teleop turtlebot3_teleop_key
```


## Saving the Map and Obtaining the Final Result

```
$ rosrun map_server map_saver -f ~/map
```


![Rivz](https://github.com/Zahrah794/TurtleBot3/assets/139267881/01004b8e-2b61-4a38-b3d5-3a6aa2658a8a)


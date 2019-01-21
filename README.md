# Map My World Robot
## Saminda Abeyruwan

### Introduction

Simultaneous Localization and Mapping (SLAM), a robot acquires a map of the environment and simultaneously localize itself relative to the map. Each robot platform contains a set of constraints on sensors, locomotion, and compute power.  SLAM approaches that address these constraints provide real-time  benefits to practitioners.  Real-Time Appearance-Based Mapping (RTAB-Map) is a an open source loop closure detection with memory management library that addresses these limitations for long-term and large scale environment mapping. This project evaluates RTAB-Map 2D and 3D mapping and localization modalities in two Gazebo environments using a RGB-D camera mounted on a four-wheeled robot. Please refer to [writeup](writeup.pdf) for detail explanation.

### Installation Instructions

Please follow the [instructions](https://github.com/samindaa/RoboND-Localization-Project)
to setup ROS Kinetic environment.

### rtabmap.db (for the supplied environment only)

The rtabmap.db for the project is available from:

```sh 
wget https://storage.googleapis.com/saminda-us-central1/udacity/rtabmap.db
```

Since rtabmap.db file is 262M, it is not uploaded to slam_project git repository. 

1. To use with rtabmap-databaseViewer:

 ```sh 
rtabmap-databaseViewer local-path-to-rtabmap.db
```

2. To use with localization.launch:

```sh 
roslaunch slam_project localization.launch database_path:=local-path-to-rtabmap.db
```

### Run the Project

First create a catkin workspace, if it is not already available.

```sh
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/
$ catkin_make
```

Then clone and build _slam_project_ project:

```sh
$ cd ~/catkin_ws/src
$ git clone https://github.com/samindaa/slam_project.git
$ cd ~/catkin_ws
$ catkin_make
$ source ~/catkin_ws/devel/setup.bash
```

To simulate the mapping tasks (execute each command in separate terminal):

1. Kitchen and Dinning world (KAD) mapping:

```sh
$ roslaunch slam_project world.launch
$ roslaunch slam_project rviz.launch
$ roslaunch slam_project teleop.launch
$ roslaunch slam_project mapping.launch
```
2. Kitchen and Dinning world (KAD) localization:

```sh
$ roslaunch slam_project localization.launch
```

3. Apartment world (APT) mapping: 

```sh
$ roslaunch slam_project apt_world.launch
$ roslaunch slam_project rviz.launch
$ roslaunch slam_project teleop.launch
$ roslaunch slam_project mapping.launch
```

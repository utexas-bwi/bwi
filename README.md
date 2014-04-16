# bwi

This repository contains top-level ROS packages for the Building Wide
Intelligence project of the University of Texas at Austin Computer
Science Department.

## Installation

### From Source

To install all the BWI components from source on Ubuntu:

First, [install ROS Hydro](http://wiki.ros.org/hydro/Installation/Ubuntu).

Then, clone the source repositories:

```
$ source /opt/ros/hydro/setup.bash
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/src
$ wstool init . https://raw.githubusercontent.com/utexas-bwi/bwi/master/rosinstall/bwi.rosinstall
```

### Source Build

```
$ cd ~/catkin_ws
$ catkin_make
$ source devel/setup.bash
```

## From Binary Packages

*Not yet available.  Coming soon.*

```
$ sudo apt-get install ros-hydro-bwi
```

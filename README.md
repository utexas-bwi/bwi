# bwi

This repository contains top-level ROS packages for the Building Wide
Intelligence (BWI) project of the University of Texas at Austin
Computer Science Department.

## BWI Repository Hierarchy

Packages contained in various released BWI repostories may depend on
other packages at the same or lower levels.  Dependencies on packages
from higher-level repositories are not permitted.

From top to bottom, the released repositories are:

 * [bwi](http://wiki.ros.org/bwi)
 * [segbot_simulator](http://wiki.ros.org/segbot_simulator)
 * [segbot_apps](http://wiki.ros.org/segbot_apps)
 * [segbot](http://wiki.ros.org/segbot)
 * [bwi_common](http://wiki.ros.org/bwi_common)

## Installation

### From Source

You can install all the BWI components normally built from source on
either ROS Hydro or Indigo.

First, [install ROS Hydro](http://wiki.ros.org/hydro/Installation/Ubuntu), 
or [Indigo](http://wiki.ros.org/indigo/Installation/Ubuntu).

Then, make sure the ROS_DISTRO environment variable is set correctly:

```
echo $ROS_DISTRO
```

It may already be.  If not, issue the appropriate one of these two
shell commands:

```
$ export ROS_DISTRO=hydro
```
or
```
$ export ROS_DISTRO=indigo
```

Next, clone the source repositories:
```
$ source /opt/ros/$ROS_DISTRO/setup.bash
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws
$ wstool init src https://raw.githubusercontent.com/utexas-bwi/bwi/master/rosinstall/$ROS_DISTRO.rosinstall
```

Install all dependencies:
```
$ rosdep install --from-paths src --ignore-src --rosdistro $ROS_DISTRO -y
```

Then, build everything:
```
$ catkin_make
$ source devel/setup.bash
```

### From Binary Packages

You may install the latest binary release, when available, from the
ROS package repository.  These may not always be the latest versions:

```
$ sudo apt-get install ros-$ROS_DISTRO-bwi-desktop-full
```

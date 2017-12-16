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
 * [segbot](http://wiki.ros.org/segbot)
 * [bwi_common](http://wiki.ros.org/bwi_common)

## Installation

### From Source

You can install all the BWI components normally built from source on
either ROS Indigo or Kinetic.

First, install ROS
[Indigo](http://wiki.ros.org/indigo/Installation/Ubuntu), or
[Kinetic](http://wiki.ros.org/indigo/Installation/Ubuntu).

The Kinetic version is only supported on Ubuntu Xenial, and is
only partially functional.

Then, make sure the ROS_DISTRO environment variable is set correctly:

```
echo $ROS_DISTRO
```

It may already be.  If not, issue the appropriate one of these two
shell commands:

```
$ export ROS_DISTRO=indigo
```
or
```
$ export ROS_DISTRO=kinetic
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
$ rosdep update
$ rosdep install --from-paths src --ignore-src --rosdistro $ROS_DISTRO -y
```

Then, build everything:
```
$ catkin build
$ source devel/setup.bash
```

Note that the **catkin build** command from the **python-catkin-tools**
package is *required* for building on ROS Kinetic.  On ROS Indigo, you
can still use **catkin_make** instead, although the newer build tool
is recommended.

### For Version 3 Robot

To use this code on the Version 3 Segway Robot, one must also define
some enviroment variables.  The steps for doing this and the specific
environment variables are described on the project wiki.  Eventually,
that should no longer be necessary.

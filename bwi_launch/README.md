# Purpose

This branch contains specially modified launch file for running SLAM on simulation environment.
The launch file will load the Gazebo world and one Segbot_v2 robot, but not move_base or localization such as amcl.
Please follow the below instruction to record new map.

## How to Run
Note that this is a specific process for running SLAM on multi-robot simulation environment.  
If you wants to run SLAM with `simulation_v2.launch`, you have to modify launch file by your own.

1. Launch Gazebo world with robot with
```
$ roslaunch bwi_launch gmapping_multi_robot.launch
```
2. Launch gmapping from segbot_navigation with
```
$ roslaunch segbot_navigation gmapping.launch
```
3. Control robot by publishing msg to /cmd_vel topic. You can use teleop_twist_keyboard from segbot_bringup.
```
$ rosrun segbot_bringup teleop_twist_keyboard
```
4. After mapped for your satisfaction, save the map to a file with
```
$ rosrun map_server map_saver -f mymap
```
Now you can replace your own map in the utexas-bwi directory to use it.

## Modify YAML file
TODO

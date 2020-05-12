# Purpose
The purpose of this branch is to generate the slam map from the Gazebo simulation environment and test it.
If you want to generate slam map, please refer instructions in `bwi_launch` directory.
If you want to test the generated slam map, please download this branch and equivalent branch on `bwi_common` repo.
**Note that** slam map is only available for north east side of GDC 3rd floor in multi_robot_simulation.
## Changes
* multi_robot_simulation.launch
  starting position of marvin & roberto changed. Now they starts at the middle of l400 hallway.
  check `$(find bwi_launch)/config/simulation.yaml` for exact coordinate of each starting point.

# How to Run a BWIbot V4 Demo

**Purpose:**
To perform a demo of the BWIbots for visitors at Anna Hiss Gym, or to test an installation of the code base on a BWIbot machine.

**Requirements:**
- a BWIbot V4
- a user account on the bot computer
- completion of the [code base installation](https://github.com/utexas-bwi/bwi/README.md)

## Instruction

As a demonstration of the BWIbots' abilities to navigate a building, avoid visitors, and perform tasks, you can use the "Visit Door List" executables that are part of the bwi_tasks package.

### Turn on the robot
1. Disconnect the battery from the wall charger: the V4 bot charger cable is connected to the back of the robot base via a serial connector.  Make sure the screws on the connector are loose before disconnecting.
2. Verify that the e-stop (red button located on the power box in the mid-section of the robot) is disengaged (pulled all the way up).
3. Press the small metal button on the power box. The base should turn on and the power button will illuminate.
4. Verify that the 3-position switch next to the power button is in the Neutral position (DIAG - NEUTRAL - BL).

You should now be able to use the robot.

### Move the robot to starting position

You will use the computer keyboard to control the robot, but first you must run the segbot launch file.  In a terminal window, type:
```
roslaunch bwi_launch segbot_v4_ahg.launch
```
Then open another terminal window to run the teleop keyboard:
```
rosrun segbot_bringup teleop_twist_keyboard
```
Follow the instructions in the teleop keyboard terminal window to move the robot into the hallway adjacent to the large gym area on level 2 of AHG.  **Before executing move commands**, reduce the robot speed settings below 0.5 by pressing "z" (speed settings will display in the terminal window).
Note that you can halt moves by pressing the spacebar.  To stop ALL robot processes and do an immediate shut-down, you can press the red E-Stop button on the power-box.  You will have to restart the robot completely afterwards.

### Orient the robot in space

1. Go to the RViz window that opened when you ran the launch file.
2. Take a look at the map and identify the robot's new location and heading in the hallway.
3.  Click the "2D pose estimate" button at the top of the RViz window to activate the tool.
4.  Move the mouse pointer to the robot's location on the map, then click and drag in the direction of heading.
5.  You should see green points around the robot indicating that the robot is sensing walls and other obstacles.

### Run the demo routine

Now you are ready to run the demo routine.  Open another terminal window and type:
```
rosrun bwi_tasks visit_door_list_smach
```
The robot will begin visiting doors on the floor.  To stop the program, type "ctrl+C", but note that the robot will continue to its next goal door before stopping.

>*If you see errors about packages for the robot arm, you must ignore the bad packages by typing:*
>```
>CATKIN_IGNORE (bad packages)
>```
>*Then build and source the workspace:*
>```
>catkin build -j6
>sws
>```

### Turn off the robot

1.  Move the robot back to its charging area in the AHG gym using the teleop keyboard program.
2.  Cancel/Kill all running ROS programs by typing "ctrl+C" in each terminal.
3.  Shutdown the computer.
4.  Press the small metal button on the power box in the middle of the robot body. The base should turn off and the power button light will turn off after a short time.  At this point you can move the bot by hand if you need to make any adjustments to its position.
5.  When the bot has powered down, plug the charger into the back of the robot base and ensure that it is securely connected using the screw terminals on the connector.

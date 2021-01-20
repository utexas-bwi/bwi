# How to Run a BWIbot Demo

**Purpose:**
To perform a demo of the BWIbots for visitors, or to test an installation of the code base on a BWIbot machine.

**Requirements:**
- a BWIbot V2 or V4
- a user account on the bot computer
- completion of the [code base installation](https://github.com/utexas-bwi/bwi)

## Instruction

As a demonstration of the BWIbots' abilities to navigate a building, avoid visitors, and perform tasks, you can use the "Visit Doors" executables that are part of the bwi_tasks package.

## For V2 Bots:
### Turn on the robot
1. Every time you start working with the robot, you should disconnect it from charging at the wall:
   - Find the cable leading from the charging brick to the robot and disconnect it. Please detach by holding the connectors only, and don't pull the connection apart using the wires as they may break off.
**Before leaving the lab, ensure that you put the robot back on charging**

2.  Change the battery mode from "Charging" to "Battery":
    - Find the panel on the robot. There is a large, three-position flip switch with the two extreme positions labeled "Charger" and "Battery". Flip from charger all the way to battery. The middle position has no specific function.

3.  Turn the laptop on.  Use the appropriate user/pass to log onto the machine.

4.  Now turn the Segway base on:
    - Locate the power buttons underneath the bottom of the Segway base. First press the **GREEN** button to power the segway base and wait 2 s. before the next step.
    - If you wish to move the robot manually, you could do so now.  The next step will turn power on to the motors, at which point you should NOT try to manually move the robot.
    - To power the segway base motors: Press the **YELLOW** button. You'll hear an audible beep and the blue light will turn on. While the segway motors and processors are on, do not move the robots manually!

You should now be able to operate the robot using the laptop.

Note: If the base beeps or shakes, the internal base battery is too low.  Allow the robot to sit with the base OFF and the main power ON (swithed to "battery") for 5 min., then try step 4 again.

### Move the robot to starting position
You will use the computer keyboard to control the robot, but first you must run the segbot launch file.  In a terminal window, type:
```
roslaunch bwi_launch segbot_v2.launch
```
Then open another terminal window to run the teleop keyboard:
```
rosrun segbot_bringup teleop_twist_keyboard
```
Follow the instructions in the teleop keyboard terminal window to move the robot into the hallway adjacent to the BWI computer lab.  **Before executing move commands**, reduce the robot speed settings below 0.5 by pressing "z" (speed settings will display in the terminal window).
Note that you can halt moves by pressing the spacebar.

### Orient the robot in space
1. Go to the RViz window that opened when you ran the launch file.
2. Take a look at the map and identify the robot's new location and heading in the hallway.
3.  Click the "(BUTTON NAME)" at the top of the RViz window to activate the tool.
4.  Move the pointer to the robot's location on the map, then click and drag in the direction of heading.
5.  You should see green points around the robot indicating that the robot is sensing walls and other obstacles.
### Run the demo routine
Now you are ready to run the demo routine.  Open another terminal window and type:
```
rosrun bwi_tasks visit_door_list
```
The robot will begin visiting doors on the floor.  To stop the program, type "ctrl+C", but note that the robot will continue to its next goal door before stopping.

### Turn off the robot
1.  Move the robot back to its charging area in the BWI computer lab using the teleop keyboard.
2.  Cancel/Kill all running ROS programs.
3.  Press the YELLOW button on the segway base to disengage the motors.
4.  Press the GREEN button on the base to turn off the segway base.  You can manually position the robot at this point if you need it closer to the charger, or otherwise move it around.
5.  Turn OFF the laptop.
6.  Plug in the charging cable.
7.  Switch the power switch on the main power box from "BATTERY" to "CHARGER".
8.  Make sure the v2 wall charger is running - it should make noise.  If not, turn it off and on again.

## For V4 Bots:
### Turn on the robot
1. Disconnect the battery from the wall charger: the V4 bot charger cable is connected to the back of the robot base via a serial connector.  Make sure the screws on the connector are loose before disconnecting.
2. Verify that the e-stop (red button located on the power box in the mid-section of the robot) is disengaged (pulled all the way up).
3. Press the small metal button on the power box. The base should turn on and the power button will illuminate.
4. Verify that the 3-position switch next to the power button is in the Neutral position (DIAG - NEUTRAL - BL).

You should now be able to use the robot.

### Move the robot to starting position
### Orient the robot in space
### Run the demo routine
### Turn off the robot

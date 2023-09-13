# How to Run a Multi-Robot BWIbot V2 Demo

**Purpose:**
To perform a demo of the multi-robot BWIbot navigation in AHG for visitors, or to test an installation of the code base on a BWIbot machine. 

**Requirements:**
- Two BWIbot V2s (flexo and bender)
- a user account on the bot computer ("bwi_demo" should be properly configured for running this demo at all times)
- completion of the [code base installation](https://github.com/utexas-bwi/bwi/README.md)

## Instruction

As a demonstration of the BWIbots' abilities to navigate a building, avoid visitors and other BWIbots, and perform tasks, you can use the "Visit Door List" executables that are part of the bwi_tasks package.

### Turn on the robots (Follow steps for both flexo and bender)
1. Disconnect the robot charging cable and the Jackery (the orange and grey power box) charging cable.

2. Plug the robot charging cable into a Jackery AC power port.  Ensure those ports are on - the button above them will be illuminated green.

3.  Turn the laptop on.  Use the appropriate user/pass to log onto the machine.

If you wish to move the robot manually, you could do so now.  The next step will turn power on to the robot motors, at which point you should NOT try to manually move the robot.

4.  Now turn the Segway base on:
    - Locate the power buttons underneath the bottom of the Segway base. First press the **GREEN** button to power the segway base and wait 2 s. before the next step.

    - To power the segway base motors: Press the **YELLOW** button. You'll hear an audible beep and the blue light will turn on. While the segway motors and processors are on, do not move the robots manually!

You should now be able to operate the robot using the laptop.

Note: If the base beeps or shakes, the internal base battery is too low.  Allow the robot to sit with the base OFF and the main power ON (swithed to "battery") for 5 min., then try step 4 again.

### Move the robot to starting position using teleop
You will use the computer keyboard to control the robot, but first you must run the segbot launch file.  In a terminal window, type:
```
roslaunch bwi_launch segbot_v2_ahg.launch
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
3.  Click the "2D pose estimate" button at the top of the RViz window to activate the tool.
4.  Move the mouse pointer to the robot's location on the map, then click and drag in the direction of heading.
5.  You should see green points around the robot indicating that the robot is sensing walls and other obstacles.
### Run the demo routine
Now you are ready to run the demo routine.  It is reccomended to get both robots to this step before continuing.  If the teleop keyboard program is still running, type "ctrl+C" in that terminal to stop it before continuing.

Open another terminal window and type:
```
rosrun bwi_tasks visit_door_list_phhp
```
The robot will begin visiting doors on the floor.  Repeat this with the second BWI bot.  To stop the program, type "ctrl+C", but note that the robot will continue to its next goal door before stopping.

### Turn off the robots
1.  Move the robots back to their respective charging areas in the BWI computer lab using the teleop keyboard command.
2.  Cancel/Kill all running ROS programs.
3.  Press the YELLOW button on the segway base to disengage the motors.
4.  Press the GREEN button on the base to turn off the segway base.  You can manually position the robot at this point if you need it closer to the charger, or otherwise move it around.
5.  Logout of the laptop.
6.  Plug in the robot charging cable into wall power and connect the barrel-plug charger to the Jackery. Make sure the Jackery AC power plugs are "ON" **Never skip step 6!**

# ROCO506Z

This Github repository implements an application in ROS to allow autonomous naviagtion of turtlebot2 in a virtual robot simulator named coppeliaSim. 
The application allows turtlebot2 to build maps of an unknown environement using scans from a laser range finder in the coppeliaSim simulation. 
The SLAM package used allows for the robot to localise in the map generated in RVIZ. The user is able to click on a point on the map and then using 
path planning the robot can follow the generated path towards the desired point. 

How to install and run this application:

To run this project, download the folder named autonomous_navigation_wss:

First, from the main project folder - autonomous_navigation_wss navigate into each sub folder below and digit: catkin_make. 
- Turtlebot_Ws 
- Turtlebot_Simulation 
- Turtlebot_Interaction 
- Turtlebot_MapNav 
- MSGS 

Open a New Terminal 
	Digit: roscore

To open coppeliaSim
	Open a New Terminal 
		Digit: coppeliaSim 

Once coppeliaSim has loaded, click on the File Dropdown and select Open Scene
	Navigate to Turtlebot_simulation folder/src/vrep_simulation/scenes
					click on the file: turtlebot2_maze_scenario.ttt
	Navigate to the Turtlebot_Wss folder. Right click in the folder and open a Terminal. 
	To source the workspace files, In the terminal command: 
					source source_all.bash

To open the Launch file of the visualization of the Turtlebot2 and the sensors in RVIZ.
	In the same terminal digit: 
		roslaunch turtlebot_rviz_launchers turtlebot_rviz.launch

For keyboard control of the robot to move around the map:
	Navigate to the Turtlebot_Wss folder. Right click in the folder and open a Terminal. 
	In the terminal command: 
		source source_all.bash 
	Then digit: 		 
		roslaunch turtlebot_teleop keyboard_teleop.launch

For Mapping and Navigation around the map: This allows you to generate a map in realtime, 
it is also responsible for the path planning and following the path trajectory, whilst trying to localise. 
	Navigate to the Turtlebot_Wss folder. Right click in the folder and open a Terminal. 
	In the terminal command: 
		source source_all.bash 
	Then digit: 		 
		roslaunch turtlebot_navigation gmapping.demo

To test the application:
	Click run on the coppeliaSim simulation. 
	Then once on RViz the turtlebot2 robot should appear.
	Add the Map, and Global and local paths. 
	Select a point on the map with the 2-D nav goal option, click on a point on the map and the arrow will set the direction that the robot will face when it completes the 	move. The robot should then create a path and move towards the point on the map.  



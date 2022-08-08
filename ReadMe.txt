The objective of this assignment is to download and install the following:
bot packages + emulator + maps
& try the navigation controls & Create a map

----------------------------------------------------------------------------

https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/


Choose your ros distribution then copy and paste the following commands 
line by line pressing Enter after each one


1- Install ROS on Remote PC

- sudo apt update
- sudo apt upgrade
- wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_noetic.sh
- chmod 755 ./install_ros_noetic.sh 
- bash ./install_ros_noetic.sh


2- Install Dependent ROS Packages

- sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
  ros-noetic-rosserial-python ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers

*This is one command, should be copied in its entirety


3- Install TurtleBot3 Packages

- sudo apt install ros-noetic-dynamixel-sdk
- sudo apt install ros-noetic-turtlebot3-msgs
- sudo apt install ros-noetic-turtlebot3


----------------------------------------------------------------------------

https://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/#gazebo-simulation

Choose your ros distribution then copy and paste the following commands 
line by line pressing Enter after each one


4- Install Simulation Package

- cd ~/catkin_ws/src/
- git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
- cd ~/catkin_ws && catkin_make


5- Launch Simulation World

- export TURTLEBOT3_MODEL=waffle
- roslaunch turtlebot3_gazebo turtlebot3_world.launch


6- Operate TurtleBot3

- roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

*This command is to control the robot inside the virtual map

----------------------------------------------------------------------------

https://emanual.robotis.com/docs/en/platform/turtlebot3/slam_simulation/


7- Run SLAM Node

- export TURTLEBOT3_MODEL=waffle
- roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping

*If the commands in step 5 do not work or there are problems with them
this can be used as an alternative
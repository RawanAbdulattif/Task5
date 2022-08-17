# Task5


Installation :
1. Download and Install Ubuntu on PC

2. Install ROS on Remote PC
Open the terminal

sudo apt update
sudo apt upgrade
wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools
chmod 755 ./install_ros_noetic.sh 
bash ./install_ros_noetic.sh

3. Install Dependent ROS Packages:

sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy
ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc
ros-noetic-rgbd-launch ros-noetic-rosserial-arduino
ros-noetic-rosserial-python ros-noetic-rosserial-client
ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server
ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro
ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz
ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers


4. Install TurtleBot3 Packages:
 sudo apt install ros-noetic-dynamixel-sdk
sudo apt install ros-noetic-turtlebot3-msgs
 sudo apt install ros-noetic-turtlebot3
 
 5. Simulation: 
5.1 Gazebo simulation: 

cd ~/catkin_ws/src/ 
git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git 
cd ~/catkin_ws && catkin_make

To launch simulation world there are three simulation environments that are prepared for TurtleBot3. We can select on of these environments to launch Gazebo.

burger
waffle
house
export TURTLEBOT3_MODEL=waffle
roslaunch turtlebot3_gazebo turtlebot3_world.launch
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

5.2 SLAM simulation
Launch Simulation World

export TURTLEBOT3_MODEL=waffle 
roslaunch turtlebot3_gazebo turtlebot3_world.launch
Run SLAM Node

export TURTLEBOT3_MODEL=waffle 
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
Run Teleoperation Node

export TURTLEBOT3_MODEL=waffle
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
source ~/.bashrc

1- In order to install TurtleBot3 packages, we need first to install ROS1 using theses commands:

    sudo apt update
    
    sudo apt upgrade
    
    wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_melodic.sh
    
    chmod 755 ./install_ros_melodic.sh
    
    bash ./install_ros_melodic.sh 
   
2- We need to install Dependent ROS1 Packages for Melodic using the following command:
    
  sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
  ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
  ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
  ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
  ros-melodic-rosserial-server ros-melodic-rosserial-client \
  ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
  ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
  ros-melodic-compressed-image-transport ros-melodic-rqt* \
  ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers
  
3- After that, I have installed TurtleBot3 packages using the following commands:

  sudo apt-get install ros-melodic-dynamixel-sdk
  
  sudo apt-get install ros-melodic-turtlebot3-msgs
  
  sudo apt-get install ros-melodic-turtlebot3
  
  mkdir -p ~/catkin_ws/src
  
  cd ~/catkin_ws/src/
  
  git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
  
  cd ~/catkin_ws && catkin_make
  
  In a new terminal, we write the following command:
  
  echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
  
  4- Naming TurtleBot3 model:
  
  There are multiple envieronments and worlds for TurtleBot, I will choose TurtleBot3 world and a robot called Waffle, so I can later create a map using SLAM.the following commands are to install theis robot and launch it in gazebo:
  
  export TURTLEBOT3_MODEL=waffle
  
  roslaunch turtlebot3_gazebo turtlebot3_world.launch
  
In order to control it, I will use the keyboard by using this command in a new terminal:

roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

![Screenshot from 2021-07-31 19-13-39](https://user-images.githubusercontent.com/85526390/127746401-909f819c-027a-4f3e-88e7-956886696983.png)

5- I will do the second part of this task, which is creating a map using SLAM simulation to show TurtleBot3 world, in a new terminal, I will use the following commands:

export TURTLEBOT3_MODEL=waffle

roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping

![Screenshot from 2021-07-31 20-21-55](https://user-images.githubusercontent.com/85526390/127747770-e3638201-585e-498a-8acb-4401ca950cab.png)


In oreder to control this robot and be enabled to scan the area using a sensor called Lidar,we use the following commands in a new terminal:

export TURTLEBOT3_MODEL=waffle

roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

![Screenshot from 2021-07-31 22-30-09](https://user-images.githubusercontent.com/85526390/127750623-7ca3e78e-c796-4550-84ea-239c6f03cf52.png)


Finally, to save this map we use the following command in a new terminal:

rosrun map_server map_saver -f ~/map

![Screenshot from 2021-07-31 22-30-09](https://user-images.githubusercontent.com/85526390/127750600-885cf8dc-99d5-4680-9ccd-5e52c365511b.png)






  

  
  

  

    
    
    
    
    

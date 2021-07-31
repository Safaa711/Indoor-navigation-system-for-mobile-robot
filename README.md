1- In order to install TurtleBot3 packages we need first to install ROS1 using theses commands:

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
  
  git clone -b melodic-devel https://github.com/ROBOTIS-GIT/DynamixelSDK.git
  
  git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
  
  git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3.git
  
  cd ~/catkin_ws && catkin_make
  
  echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
  

  

    
    
    
    
    

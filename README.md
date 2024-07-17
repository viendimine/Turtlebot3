# Turtlebot3

![turtlebot3-burger-logo](https://github.com/viendimine/Turtlebot3/assets/126682925/96abf169-3e25-451f-9c34-8007a8ec16fe)


## Jetson-Nano (Setup)
The Jetson Nano is a compact, powerful AI computer designed by NVIDIA, ideal for developing AI applications. It features a 128-core Maxwell GPU, a quad-core ARM Cortex-A57 CPU, and supports CUDA, TensorRT, and other AI frameworks. It is capable of running multiple neural networks in parallel, making it suitable for projects like robotics, image processing, and smart home devices. With 4GB of LPDDR4 memory and a rich set of I/O ports, it provides extensive connectivity and expandability options for developers.

![jetson-nano-dev-kit-top-r6-HR-B01](https://github.com/viendimine/Turtlebot3/assets/126682925/3bbf76df-2245-413d-a958-f4bbb80b0a59)
![Screenshot_2024-06-28_20-35-01](https://github.com/viendimine/Turtlebot3/assets/126682925/a0d93ee1-538e-4cce-8659-160fa4fdc438)

## PC Setup

### Install ROS on Remote pc
```
$ sudo apt update
$ sudo apt upgrade
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_noetic.sh
$ chmod 755 ./install_ros_noetic.sh 
$ bash ./install_ros_noetic.sh
```

### Install Dependent ROS package
```
$ sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
  ros-noetic-rosserial-python ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers
```

### Install TURTLEBOT3 packages
```
$ sudo apt-get install ros-noetic-dynamixel-sdk
$ sudo apt-get install ros-noetic-turtlebot3-msgs
$ sudo apt-get install ros-noetic-turtlebot3
```
### Set TurtleBot3 Model Name
* For TURTLEBOT3 Burger
```
$ echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
```
* For TURTLEBOT3 Waffle Pi
```
$ echo "export TURTLEBOT3_MODEL=waffle pi" >> ~/.bashrc
```
### Network Configuration

![Screenshot_2024-07-07_19-44-32](https://github.com/viendimine/Turtlebot3/assets/126682925/495851e4-7389-4502-bfff-d3c158815c80)

```
$ export ROS_MASTER_URI=http://IP_OF_REMOTE_PC:11311
$ export ROS_HOSTNAME=IP_OF_TURTLEBOT
```
Connect PC to a WiFi device and find the assigned IP address with the command below.
```
$ ifconfig
```

Open the file and update the ROS IP settings with the command below.

```
$ nano ~/.bashrc
```
Source the bashrc with below command.
```
$ source ~/.bashrc
```

### SBC setup

#### ROS Network Configuration
Confirm the WiFi IP address

```
$ ifconfig
```
#### Edit the .bashrc file
```
$ nano ~/.bashrc
```

```
$ export ROS_MASTER_URI=http://{IP_ADDRESS_OF_REMOTE_PC}:11311
$ export ROS_HOSTNAME={IP_ADDRESS_OF_RASPBERRY_PI_3}
```

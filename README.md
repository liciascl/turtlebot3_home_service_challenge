# Turtlebot3 Home Service Challenge(with InsperBot)

[![noetic-devel Status](https://github.com/ROBOTIS-GIT/turtlebot3_home_service_challenge/workflows/noetic-devel/badge.svg)](https://github.com/ROBOTIS-GIT/turtlebot3_home_service_challenge/tree/noetic-devel)

![https://raw.githubusercontent.com/liciascl/turtlebot3_home_service_challenge/master/img/print.png](https://raw.githubusercontent.com/liciascl/turtlebot3_home_service_challenge/master/img/print.png)

### Requeriments

- Ubuntu 20.04
- ROS Noetic
- Opencv4

**NOTE:** We have a guide for setup your system with this Requirements **[here](https://github.com/Insper/insperbot/wiki/How-Setup-your-Ubuntu-20.04)** 

### How to Run

clone the repository:

```bash
git clone https://github.com/liciascl/turtlebot3_home_service_challenge.git

cd ~/catkin_ws
catkin_make
```

### Edit .bashrc

Add this lines in your .bashrc

```bash
export TURTLEBOT3_MODEL=burger
export LC_NUMERIC="en_US.UTF-8"
export GAZEBO_MODEL_PATH=$HOME/catkin_ws/src/my_simulation/models:${GAZEBO_MODEL_PATH}
```


### Run the scenario

```
roslaunch turtlebot3_home_service_challenge_simulation competition.launch

```


### To Enable gripper control

```
roslaunch mybot_description mybot_control2.launch     

```

### How to control the robot’s gripper

### Arm (joint1):

![https://raw.githubusercontent.com/Insper/insperbot/main/image/arm.gif](https://raw.githubusercontent.com/Insper/insperbot/main/image/arm.gif)

```bash
Up: 1.5
Forward : 0
Down : -1.5

rostopic pub -1 /joint1_position_controller/command std_msgs/Float64 "data: 0"
```

### Gripper (joint2 and joint3)

![https://raw.githubusercontent.com/Insper/insperbot/main/image/gripper.gif](https://raw.githubusercontent.com/Insper/insperbot/main/image/gripper.gif)

```bash
Closed: 0
Open: -1
rostopic pub -1 /joint2_position_controller/command std_msgs/Float64 "data: 0"
```

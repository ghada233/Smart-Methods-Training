ROS

> ROS-melodic-and-Robotic-Arm-packages-installaion-on-ubuntu-20.04

installing robot operating system (ROS) melodic on ubuntu 20.04 and setting up environment tutorial along with robotic arm packages and dependencies installation
-------------------------------------------------------------------------------------------------------------------------------------------------------------------

I was unable in installing ROS Noetic on Ubuntu 22.04 I ran across a number of problems and was unable to use my virtual gadget.
That's why I set up the compatible with Ubuntu 20.04 ROS melody version. 
The steps and materials required to install ROS and the robotic arm packages are shown in this repository.

------------------------------------------------------------------------------------------------------------------------
:beginner:
## 1. INSTALLING Step 

- installing VM by using this link https://www.virtualbox.org/  :white_check_mark:

- then installing iso file for ubuntu verison 20.04 by using this link https://releases.ubuntu.com/20.04/  :white_check_mark:

>pic
![Picture1](https://user-images.githubusercontent.com/70041510/186390051-62b1f3e7-77c9-4734-a24b-26dc2ea2af40.png)


:beginner:
## 2.INSTALLING ROS 

It is typical to use the terminal commands given by the program authors to install or update any software on Ubuntu.
So, opening the terminal is the first step. After that, install ROS melodic on Ubuntu by following 
the [Ros instructions](https://linuxopsys.com/topics/install-ros-noetic-on-ubuntu) , which are as follows:

~~~
echo "deb http://packages.ros.org/ros/ubuntu focal main" | sudo tee /etc/apt/sources.list.d/ros-focal.list
~~~

and complet all instructure

Installing curl commands

~~~
$ sudo apt install curl
~~~

Setting up keys

~~~
$ curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

~~~

Installing ROS
~~~
$ sudo apt update
Then installing Desktop-Full that contains all important libraries.
~~~
~~~
$ sudo apt install ros-melodic-desktop-full
~~~
A message saying that additional disk space is required, Do you want to continue?[y/n] will appear, enter :
~~~
y
~~~

Just make sure you have 2GB or more of free space before entering y. If not, maximize the machine's space in the virtual machine settings. 
Depending on the internet connection, the downloading procedure will take some time.

------------------------------------------------------------------------------------------------------------

3. ROBOT ARM PACKEGES SETUP :minidisc:

I used the [Smart-methods](https://github.com/smart-methods/arduino_robot_arm/) guide, which I followed to install the Robotic Arm package as follows:
Installation of dependencies These steps will install necessary plugins and packages to demonstrate 
and operate the robotic arm; when prompted to install in exchange for additional space, choose Y. It will also request a password.

~~~
$ git clone https://github.com/smart-methods/arduino_robot_arm.git 
$ cd ~/catkin_ws
$ rosdep install --from-paths src --ignore-src -r -y
$ sudo apt-get install ros-melodic-moveit
$ sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui
$ sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher
$ sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control
~~~

The last stages will be once installation is complete:

~~~
$ catkin_make
$ sudo nano ~/.bashrc
~~~

Return to the terminal now, and type:

~~~
$ source ~/.bashrc
~~~

Run this to launch Rviz and the Gazebo Simulator:
~~~
$ roslaunch robot_arm_pkg check_motors.launch
~~~

The robotic arm is now under your control

>pic

![Picture2](https://user-images.githubusercontent.com/70041510/186390100-fe82c7c1-54be-4909-abeb-78a73827ab19.png)




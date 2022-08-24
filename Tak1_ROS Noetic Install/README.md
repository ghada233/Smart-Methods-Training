## ROS Noetic Install on jetson nano (Ubuntu 20.04)

The official Noetic setup page, which can be found here:[link](http://wiki.ros.org/noetic/Installation/Source), is where this instruction is based.

This version adds several changes for missing packages in the Jetson nano OS's Ubuntu 20.04 distribution.
I believe the majority of Ubuntu 20.04 installs should be compatible with this installation, but I cannot promise it.

>System and python dependencies
~~~
sudo apt install build-essential
sudo -H python3 -m pip install -U pip
sudo -H python3 -m pip install -U setuptools
sudo -H python3 -m pip install -U rosdep rosinstall_generator vcstool
sudo rosdep init
rosdep update

mkdir ~/ros_catkin_ws
cd ~/ros_catkin_ws
~~~
-------------------------------

>Generate rosinstall file
>
~~~
rosinstall_generator robot perception --rosdistro noetic --deps --tar > noetic-robot-perception.rosinstall
mkdir ./src
vcs import --input noetic-robot-perception.rosinstall ./src
~~

----------------------

>Install ros packages
by this link  https://github.com/ghada233/Smart-Methods-Training/tree/main/Task1_ROS

 and finish :electric_plug:

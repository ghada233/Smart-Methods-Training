Building_SLAM_map_with_TURTLEBOT3 :keyboard:
-----------------------------------------------

Simultaneous Localization and Mapping (SLAM), one of the most useful nodes in ROS, uses the robot's sensors to explore and map its surroundings.
The SLAM approach may be applied to a variety of robots; in this instance, I used the turtle bot burger.

>First, I followed the  [instructions](https://emanual.robotis.com/docs/en/platform/turtlebot3/overview/#overview) to install 
>the necessary dependencies, turtlebot, gazebo, and SLAM simulation programs.

I attempted to execute the following commands after making sure that all packages had been correctly installed:
---------------------

~~~
$ Roscore
~~~

Launching gazebo In another terminal:
-----------------------------
~~~
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
~~~
 

I'm opening a second terminal so I can utilize SLAM and see the burgerbot explore its surroundings:
-----------

~~~
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
~~~

I can now use the keyboard to direct the robot's movements:
---------

~~~
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

~~~

the final map
-----
![Picture3](https://user-images.githubusercontent.com/70041510/186393493-bf735eef-3f0c-4c4a-9705-9642dbc0ea72.png)

i take save by use prt sc 

but we can use this comaand 
~~~
$ rosrun map_server map_saver -f /tmp/my_map`

~~~

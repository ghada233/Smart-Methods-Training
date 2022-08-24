Turtlebot3 :minidisc:

>Turtlebot3_navigation_with_SLAM

Simultaneous Localization and Mapping (SLAM), one of the most useful nodes in ROS, uses the robot's sensors to explore and map its surroundings. The SLAM approach may be applied to a broad variety of robots.
I made an effort to virtually navigate using the map that turtlebot3 has stored in this repository. [Last verion](https://github.com/ghada233/Smart-Methods-Training/tree/main/Task2_SLAM)

I first had to start Gazebo:
---------
~~~
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
~~~

executing the navigation node after that:

~~~~
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml
~~~~

The previously stored map will now appear, and I must move the robot and choose 2D posture estimation so that the lidar sensors' data matches the map.
![Picture6](https://user-images.githubusercontent.com/70041510/186397548-cdf5f911-c3ea-4cea-8d39-da7a85eeef80.png)


>now use a keyboard to move the bot:
~~~
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
~~~
![Picture5](https://user-images.githubusercontent.com/70041510/186397193-88db99fd-5330-44bd-83fa-29c9811554ae.png)

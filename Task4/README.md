diff_drive_bot
>Building_SLAM_map_with_differential_drive_robot

I tried to construct a SLAM map of the Differential Drive Robot I discovered link here https://github.com/devanshdhrafani/diff_drive_bot
in this repository. I set up a catkin workspace and installed all the required packages in accordance with the directions.

In order to control the robot using the real world and models, I then opened Gazebo:
~~~
$ roslaunch diff_drive_bot gazebo.launch 
~~~

I had trouble starting Gazebo, so I changed the config.yaml file to use the new URL,
https://api.ignitionrobotics.org, in favor of the previous one, https://api.ignitionfuel.org.

The SLAM mapping node was then started:

~~~
$ roslaunch diff_drive_bot gmapping.launch
~~~

>After that, I attempted to run keyboard teleop.py to operate the robot, but it was completely unsuccessful. 
>As you can see, the turtlebot3 teleop program I launched in its place worked remarkably well to operate this robot!
---------------------

~~~
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
~~~
![Picture7](https://user-images.githubusercontent.com/70041510/186400389-fb045c60-072e-44fd-988c-6ace417e38f2.png)

Finally, I used: to save the map
~~~
$ rosrun map_server map_saver -f ~/test_map
~~~
The final map:

![Picture8](https://user-images.githubusercontent.com/70041510/186400898-5999b1be-0469-4001-aaab-cbb068c04cf2.png)

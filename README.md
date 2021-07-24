# Bluilding-SLAM-map-with-TURTLEBOT3
### SLAM (Simultaneous Localization and Mapping) is one of the most useful nodes in ROS, where it uses the robot's sensors to explore and draw a map of the surroundings. We can use SLAM approach with a variety of robots, in this repository I used turtlebot burger.
#### First, I installed the dependencies, turtlebot packages, gazebo and SLAM simulation packages by following [these instructions](https://emanual.robotis.com/docs/en/platform/turtlebot3/overview/#overview).


#### After checking that all packages were installed properly, I tried to run these commands:

```
$ Roscore
```

Launching gazebo In another terminal:
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```


Openning another terminal so I can use SLAM and see the burgerbot trying to discover the environment:
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```


Now I can control the robot's movements using keyboard:
```
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

```

the resulting map would be like this:



![map](https://user-images.githubusercontent.com/83130573/126866312-ae729bc2-57d9-4f57-821b-4d51fa09571a.png)



I saved the map by running this command:
```
$ rosrun map_server map_saver -f /tmp/my_map`

```

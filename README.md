# Basic Install

1. Create catkin workspace

```
mkdir -p ~/pioneer3at_ws/src
cd ~/pioneer3at_ws/src
catkin_init_workspace
```

1. Clone repository

```
cd ~/pioneer3at_ws/src
clone https://github.com/nkoenig/pioneer3at_demo
```

1. Build

```
cd ~/pioneer3at_ws
catkin_make install
```

1. Run Gazebo

```
cd ~/pioneer3at_ws
source install/setup.bash
roslaunch p3at_description p3at.launch
```

1. In another terminal, run the ros control code

```
cd ~/pioneer3at_ws
source install/setup.bash
rosrun p3at_plugin p3at
```

# Multi-Robot Usage

The [p3at_description](p3at_description) package now also contains examples for spawning multiple robots. The [spawn_p3at.launch](p3at_description/launch/spawn_p3at.launch) file spawns a robot with arguments ```robot_name``` (name used to distinguish different robots) and ```pose_args``` (for specifying the spawn pose). All relevant topics are published under the namespace as given by the ```robot_name``` argument. 

A example of usage to spawn 2 robots into an empty world can be started via
````
roslaunch p3at_description empty_world_multi_robot_example.launch
```

If you want to really tax your machine, you can try
```
roslaunch p3at_description lots_of_robots.launch
```
This spawns 100 P3ATs and demonstrates how the spawn script described previously can be used to quickly generate large test scenarios. Note that after spawning all robots, the system requires about 9Gbytes of RAM.

![](https://github.com/nkoenig/pioneer3at_demo/wiki/images/army_of_pioneers.png)


# Project

Modify code in `~/pioneer3at_ws/src/pioneer3at_demo/p3at_plugin/src/p3at.cc`
to driver the P3AT so that it doesn't hit opstacles.

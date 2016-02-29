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

# Project

Modify code in `~/pioneer3at_ws/src/pioneer3at_demo/p3at_plugin/src/p3at.cc`
to driver the P3AT so that it doesn't hit opstacles.

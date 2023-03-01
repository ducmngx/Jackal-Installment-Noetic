### Install dependencies :

This is *manual* way to install necessary packages :
```
sudo apt-get install ros-noetic-robot-localization ros-noetic-controller-manager ros-noetic-joint-state-controller ros-noetic-diff-drive-controller ros-noetic-gazebo-ros ros-noetic-gazebo-ros-control ros-noetic-gazebo-plugins             ros-noetic-lms1xx ros-noetic-pointgrey-camera-description ros-noetic-roslint ros-noetic-amcl ros-noetic-gmapping      ros-noetic-map-server ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro ros-noetic-message-runtime ros-noetic-topic-tools ros-noetic-teleop-twist-joy
```
If you want to use `rosdep` and install all dependencies (for example for doc generation etc), the skip this step.


### Create a workspace and clone sources
```
mkdir -p jackal_ws/src; cd jackal_ws/src; catkin_init_workspace
git clone https://github.com/jackal/jackal.git
git clone https://github.com/jackal/jackal_simulator.git
git clone https://github.com/jackal/jackal_desktop.git
git clone https://aur.archlinux.org/ros-noetic-interactive-marker-twist-server.git
```

*Install dependencies with* `rosdep` : 
```
cd jackal_ws; rosdep install --from-paths . --ignore-src --rosdistro=noetic
```

### Build and source

```
cd jackal_ws; catkin_make; source devel/setup.bash
```
### Start simulation : 

In terminal 1 :
```
roslaunch jackal_gazebo jackal_world.launch config:=front_laser gui:=false
```
In terminal 2 :
```
roslaunch jackal_viz view_robot.launch
```
and follow the [tutorial](https://www.clearpathrobotics.com/assets/guides/noetic/jackal/simulation.html)

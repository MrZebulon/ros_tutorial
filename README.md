# 1. Introduction

This tutorial explains how to install and setup [ROS Noetic](https://wiki.ros.org/noetic/) on linux.
Noetic requires you to run Ubuntu 20 LTS (check your version via  ```lsb_release -a```)

# 2. Installing ROS Noetic
Add ROS packages to your package list
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo apt update
```

Install Ros
```sudo apt install ros-noetic-desktop``` or ```sudo apt install ros-noetic-desktop-full```

Then install packages and start setting up
```
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
sudo rosdep init
rosdep update
```

# 3. Setting up your dev environment

ROS should be called each time you open your terminal, you may automate this:
```
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

Next, you must create your worksapce, it should be located in your home folder
```
cd ~
mkdir -p catkin_ws/src
cd catkin_ws
catkin_make
. ~/catkin_ws/devel/setup.bash
```

Once this is done, make sure you are in the *catkin_ws/src folder*. We'll now create a new package
```
catkin_create_pkg <package_name> <dependencies>
````
To build your package, use:
```
catkin_make
catkin_make install (optional)
```

# 4. What's next ?

Here's a list of [ROS tutorials](https://wiki.ros.org/ROS/Tutorials), check them out. Especially useful to get more familiar with the ROS development workflow.

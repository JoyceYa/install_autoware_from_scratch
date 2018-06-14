# General Infrustructure

## Basic Ubuntu Packages

```
sudo apt-get update
sudo apt-get install gcc g++ git vim
```

## ROS for Autoware

Distribution: (Kinetic)[http://wiki.ros.org/kinetic/Installation/Ubuntu]

Setup your `sources.list`:

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

Set up your keys:

```
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116
```

Installing ROS Packages for Autoware:

```
sudo apt-get update
sudo apt-get install ros-kinetic-desktop-full ros-kinetic-nmea-msgs ros-kinetic-nmea-navsat-driver ros-kinetic-sound-play ros-kinetic-jsk-visualization ros-kinetic-grid-map ros-kinetic-gps-common
sudo apt-get install ros-kinetic-controller-manager ros-kinetic-ros-control ros-kinetic-ros-controllers ros-kinetic-gazebo-ros-control ros-kinetic-joystick-drivers
sudo apt-get install libnlopt-dev freeglut3-dev qtbase5-dev libqt5opengl5-dev libssh2-1-dev libarmadillo-dev libpcap-dev gksu libgl1-mesa-dev libglew-dev python-wxgtk3.0 software-properties-common libmosquitto-dev libyaml-cpp-dev python-flask python-requests
```

Initializing `rosdep`:

```
sudo rosdep init
rosdep update
```

Environment setup:

```
echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

Creating and building a catkin workspace:

```
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
```

Environment setup for catkin workspace:

```
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
```


# Autoware

## Installing Autoware from Source

References:
  - https://github.com/CPFL/Autoware

Building Autoware from source:

```
cd $HOME
git clone https://github.com/CPFL/Autoware.git
cd ~/Autoware/ros/src
catkin_init_workspace
cd ../
./catkin_make_release
```


## Installing Autoware with Docker

References:
  - https://github.com/CPFL/Autoware/wiki/Generic-x86-Docker
  - https://github.com/CPFL/Autoware/tree/master/docker/generic (run `build.sh`)



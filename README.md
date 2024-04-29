# Drone Simulation

// prerequisite
1. Ubuntu Installation
2. Ros Installation
[ref](https://velog.io/@emdydqortkgh/ROS-Noetic-%EC%84%A4%EC%B9%98-Ubuntu-20.04)
```
$ sudo apt-get install -y chrony ntpdate
$ sudo ntpdate -q ntp.ubuntu.com
$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
$ sudo apt install curl
$ url -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
$ sudo apt update
$ sudo apt install ros-noetic-desktop-full
$ echo "source /opt/ros/noetic/setup.bash"
$ source ~/.bashrc
$ sudo apt install python3-rosdep
$ sudo rosdep init
$ rosdep update
$ sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```
3. Gazebo Installation
[ref](https://classic.gazebosim.org/tutorials?tut=install_ubuntu)
```
$ curl -sSL http://get.gazebosim.org | sh
```

[ref](https://mkdrone.tistory.com/2)



// setup

// URDF

URDF: Unified Robot Description Format

로봇의 구조와 형태를 기술하는 파일. XML형식. Link와 Joint로 구성.

geometry(링크의 형태), origin(링크의 시작점), material(링크의 재료), inertia(링크의 관성정보)를 포함.

솔리드웍스, 퓨전360 등의 3D 모델링 프로그램을 통해 모델링 후 URDF exporter를 통해 변환.

Q. Key가 무엇인가?

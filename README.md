# Ubuntu Installation
Method 1: Multi Boot with Windows and Ubuntu</br>
Installation Steps
  1. Go to the [official Ubuntu website](https://ubuntu.com/download) and download the latest version of the Ubuntu ISO file.
  2. Create a Bootable USB Drive. (Rufus)
  3. Make a space for new OS by shrinking existing disk.
  4. Boot your computer with the USB drive and install Ubuntu.
Method 2: Virtual Machine


## Drone Simulation

### prerequisite
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
### drone simulation

[ref](https://mkdrone.tistory.com/2)
```
mkdir <> # <>: directory name
git clone https://github.com/ArduPilot/ardupilot

cd <> # ardupilot 설치 디렉토리로 이동
git init
git submodule update --init --recursive # 추가 패키지 설치

git clone https://github.com/khancyr/ardupilot_gazebo
cd ardupilot_gazebo
mkdir build
cd build
cmake ..
make -j4
sudo make install

sudo apt update
sudo apt install python3-pip

pip3 install pymavlink

sudo apt-get install python3-dev python3-opencv python3-wxgtk4.0 python3-pip python3-matplotlib python3-lxml python3-pygame
pip3 install PyYAML mavproxy --user
echo "export PATH=$PATH:$HOME/.local/bin" >> ~/.bashrc

gazebo --verbose worlds/iris_arducopter_runway.world
```

// URDF

URDF: Unified Robot Description Format

로봇의 구조와 형태를 기술하는 파일. XML형식. Link와 Joint로 구성.

geometry(링크의 형태), origin(링크의 시작점), material(링크의 재료), inertia(링크의 관성정보)를 포함.

솔리드웍스, 퓨전360 등의 3D 모델링 프로그램을 통해 모델링 후 URDF exporter를 통해 변환.

// 버전관리, 가상환경(virtual environment), 개발환경 관리





Q. Key가 무엇인가? (ros installation)

Q. Docker와 distrobox는 무엇인가?

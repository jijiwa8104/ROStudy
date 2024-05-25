# Ubuntu Installation
Method 1: Multi Booting</br>
Installation Steps
  1. Go to the [official Ubuntu website](https://ubuntu.com/download) and download the latest version of the Ubuntu ISO file.
  2. Create a Bootable USB Drive. (Use Rufus or Etcher)
  3. Make a space for new OS by shrinking existing disk.
  4. Boot your computer with the USB drive and install Ubuntu.

Method 2: Virtual Machine</br>

# How to manage packages on a per-project basis in Ubuntu
1. Vurtual Environment(virtualenv or venv for Pyhton)
2. Contatiner Technology like Docker


# ROS Installation
- Version Match Ubuntu and ROS

There are several distributions of Ubuntu and each has a appropiate ROS version.</br>
Ubuntu 20.04(Focal Fossa) -> ROS Noetic Ninjemys</br>

- Do I have ROS installed already?
```
~$ rosversion -d
```

- Steps to install ROS
```

```

# What is Symbolic Links
Symbolic Links are special files in the file system that store references to other files or directories.</br>
They provide a way to access another file indirectly through a specific path.</br>
In Linux systems like Ubuntu, /bin/sh is typically linked to dash or another shell program like bash.</br>
This setup allows for flexibility and performance optimization.</br>
For instance, dash might be used for system boot scripts or initialization tasks due to its lightweight nature, while bash might be preferred for interactive shell sessions due to its richer feature set.</br>
'/bin/sh'가 'dash'로 링크되었다 -> '/bin/sh'가 'dash' 프로그램을 가리키는 심볼릭 링크이다.</br>
```
~$ which sh      # sh 명령어가 실제로 가리키는 경로
/usr/bin/sh      # 아 sh 명령어는 이 경로의 sh 파일을 가리키구나.

~$ ls -l /bin/sh      # ls는 파일 시스템의 대상 경로의 파일 목록나 대상 파일의 정보 표시하라는 명령어; -l 옵션은 자세한 정보; /bin/sh는 궁금한 대상 파일
lrwxrwxrwx 1 root root 4  4월 27 23:17 /bin/sh -> dash      # 'l' 파일의 유형이 심볼릭 링크구나; 'rwx' 대상 파일 권한; 'dash' 심볼릭 링크가 가리키는 실제 파일
# /usr/bin/sh 실행 시 실제로 실행되는 프로그램은 dash

~$ readlink -f /bin/sh      # /bin/sh가 가리키는 실제 파일의 절대경로(-f)
/usr/bin/dash
```

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

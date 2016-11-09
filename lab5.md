## Lab5: 安装ROS ##


### 实验任务 ###

 Robot operation system，一套框架，底层提供硬件驱动，软件层面支持通用的文件格式。毕竟穷，买不起一个150K的激光雷达，我们主要用它的仿真功能。本周任务就是安装ROS。

### Installation ###

**1.Configure your Ubuntu repositories**


**2.Setup your sources.list**

>sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

**3.Set up your keys**
>sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116

**4.Installation**

First, make sure your Debian package index is up-to-date:
>sudo apt-get update

Desktop-Full Install: (Recommended) : ROS, rqt, rviz, robot-generic libraries, 2D/3D simulators, navigation and 2D/3D perception
>sudo apt-get install ros-kinetic-desktop-full

To find available packages, use:
>apt-cache search ros-kinetic

**5.Initialize rosdep**

Before you can use ROS, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS.
>sudo rosdep init

>rosdep update

**6.Environment setup**

It's convenient if the ROS environment variables are automatically added to your bash session every time a new shell is launched:

>echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
source ~/.bashrc

**7.Getting rosinstall**

To install this tool on Ubuntu, run:
>sudo apt-get install python-rosinstall

**8.Setup your sources.list**

### 实验结果 ###

这里上网找了一个简单例子进行了测试

**1.在Terminal中输入下诉命令.**

我的理解是,该命令是初始化ROS环境,全局参数,以及每个节点注册等工作.
 >  $ roscore

**2.再打开一个Terminal,输入下诉命令.开启一个小乌龟界面**
>    $ rosrun turtlesim turtlesim_node]

![](http://tuku02-qn.icp114.cn/public/16-11-9/11884868.jpg)

**3.打开第三个终端，输入以下指令，接收键盘输入，控制小乌龟移动**
>$ rosrun turtlesim turtle_teleop_key

**4.选中最后打开的Terminal,键盘按下上下左右按键,可看到控制小乌龟移动.**

![](http://tuku02-qn.icp114.cn/public/16-11-9/69442372.jpg)

**5. 再打开一个Terminal,输入下诉命令,可以看到当前ROS nodes以及Topic等图形展示..**
>    $ rosrun rqt_graph rqt_graph

![](http://tuku02-qn.icp114.cn/public/16-11-9/24848682.jpg)

因此，安装成功。
###实验感想###

这次实验比较简单，只是安装一下ros，和简单的熟悉一下其使用，只要按照教程来就没有遇到什么问题。


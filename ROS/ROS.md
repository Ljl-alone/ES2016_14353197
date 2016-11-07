# 配置ROS
* * *
* ROS简介
   ROS——Robot operation system，一套框架，底层提供硬件驱动，软件层面支持通用的文件格式。可用于仿真。
* 安装过程
教程参考：*[Ubuntu 14.04 15.04](http://wiki.ros.org/jade/Installation/Ubuntu)*   *[Ubuntu 15.10 16.04](http://wiki.ros.org/kinetic/Installation/Ubuntu)*
   1. Configure your Ubuntu repositories
   2. Setup your sources.list
     * sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
   3. Set up your keys
     * sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116
   4. Installation
     * sudo apt-get update
     * sudo apt-get install ros-jade-desktop-full
     * apt-cache search ros-jade
   5. Initialize rosdep
     * sudo rosdep init
     * rosdep update
   6. Environment setup
     * echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
     * source ~/.bashrc
   7. Getting rosinstall
     * sudo apt-get install python-rosinstall
* 实验截图
    * 最终执行完所有指令，结果为：
		![图片1](https://raw.githubusercontent.com/Ljl-alone/ES2016_14353197/master/ROS%E5%9B%BE%E7%89%871.png)
        ![图片2](https://raw.githubusercontent.com/Ljl-alone/ES2016_14353197/master/ROS%E5%9B%BE%E7%89%872.png)
* 实验感想
     本次实验主要是进行了ROS的安装，按照实验教程按部就班复制粘贴洗完澡出来就安装好了<(￣︶￣)>




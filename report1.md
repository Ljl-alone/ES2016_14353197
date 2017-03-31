# OpenCL & OpenCV环境配置实验报告

## 实验环境
- 虚拟机下进行配置 操作系统为 64位 Ubuntu 16.04

## 主要配置过程及截图
具体见实验教程
#### OpenCV配置
> 1.安装依赖
```bash
sudo apt-get install build-essential libgtk2.0-dev libjpeg-dev libtiff5-dev libjasper-dev libopenexr-dev cmake libeigen3-dev yasm libfaac-dev libtheora-dev libx264-dev libv4l-dev libavcodec-dev libavformat-dev libswscale-dev libv4l-dev ffmpeg
```
> 2.编译安装配置链接库：
```bash
cd opencv-
mkdir release
cd release
cmake -D MAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D WITH_OPENCL=OFF -D WITH_CUDA=OFF ..
make
sudo make install
sudo /bin/bash -c 'echo "/usr/local/lib" > /etc/ld.so.conf.d/opencv.conf'
sudo ldconfig
```
> 3.验证：
```bash
make
./DisplayImage <picture path here>
#将<picture path here>替换为任意一张图片的路径
```
弹出窗口显示出对应的图片，则安装成功,如下所示
![](http://a4.qpic.cn/psb?/V12HqRbI3kMzfl/oO1d3AR3WyQ3O21QPHXy8XU1zAGH0E8LKZncPlY3tM8!/b/dBcBAAAAAAAA&ek=1&kp=1&pt=0&bo=rwOAAsUDjwIDCEg!&tm=1490943600&sce=60-3-3&rf=viewer_311)


#### OpenCL配置
本实验使用Intel CPU作为并行设备，选择安装Intel SDK
> 1.安装SDK
```bash
sudo apt install dkms xz-utils openssl libnuma1 libpciaccess0 bc curl libssl-dev lsb-core libicu-dev
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
echo "deb http://download.mono-project.com/repo/debian wheezy main" | sudo tee /etc/apt/sources.list.d/mono-xamarin.list
sudo apt-get update
sudo apt-get install mono-complete
sudo sh install_GUI.sh
```
> 2.验证
```bash
sudo apt-get install clinfo
clinfo
```
能看到平台和设备就说明成功安装,如下所示
![](http://a4.qpic.cn/psb?/V12HqRbI3kMzfl/hpOKp4OYNEB5Uy2QQ*MX*YGU6Y11aMMLm3ESCtm..Zo!/b/dBcBAAAAAAAA&ek=1&kp=1&pt=0&bo=fQNNAn0DTQIDCC0!&tm=1490943600&sce=50-1-1&rf=viewer_311)

## 遇到的问题
#### 一、ffmpeg在Ubuntu14.04中被移除
解决方法：
1.在网上找到另一种种方法安装
```bash
sudo add-apt-repository ppa:mc3man/trusty-media
sudo apt-get update
sudo apt-get install ffmpeg gstreamer0.10-ffmpeg
```
2.更新至Ubuntu16.04也行

#### 二、32位系统安装出错
![](http://a1.qpic.cn/psb?/V12HqRbI3kMzfl/GVqjtJ3SjPwfyEZHOLf..MzjVL5j4uORpruVhv1cX4I!/b/dCABAAAAAAAA&ek=1&kp=1&pt=0&bo=SgNaAkoDWgIDCC0!&tm=1490943600&sce=50-1-1&rf=viewer_311)

解决方法
1. 换成64位系统进行安装




## 实验感想
- 本次试验难度不大，照着实验教程做就是了。坑就是老版本Ubuntu 14.04移除了ffmpeg，而且虚拟机下不能用32位系统，只能用64位系统。

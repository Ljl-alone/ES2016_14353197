# ES2016_14353197
## Lab

1.DOL框架描述：
* 分布式操作层（DOL）是一个针对程序并行应用的一个软件开发框架,该框架允许定制化基于Kahn进程网络模型计算的应用，并且具有一个基于SystemC仿真引擎，此外，DOL提供了一个基于XML的特定格式，来描述在多处理器系统上并行应用的实现，包括绑定和映射。

2.DOL安装笔记
* 安装一些必要的环境：
      $	sudo apt-get update
      $	sudo apt-get install ant
      $    sudo apt-get install openjdk-7-jdk
      $	sudo apt-get install unzip
* 解压文件、编译systemc
   - 新建dol的文件夹 $	mkdir dol    
   - 将dolethz.zip解压到 dol文件夹中 $ unzip dol_ethz.zip -d dol
   - 解压systemc  $	tar -zxvf systemc-2.3.1.tgz
   - 解压后进入systemc-2.3.1的目录下 $	cd systemc-2.3.1
   - 新建一个临时文件夹objdir   $	mkdir objdir
   - 进入该文件夹objdir  $	cd objdir
   - 运行configure(能根据系统的环境设置一下参数，用于编译)
   - $	../configure CXX=g++ --disable-async-updates
   - 编译 $	sudo make install
   - 记录当前的工作路径(会输出当前所在路径，记下来，待会有用) $	pwd
* 编译dol
   - 进入刚刚dol的文件夹 $	cd ../dol  修改build_zip.xml文件:
   ```<property name="systemc.inc" value="YYY/include"/>
<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>
```把YYY改成上页pwd的结果（注意，对于  64位 系统的机器，lib-linux要改成lib-linux64）
   - 然后是编译 $	ant -f build_zip.xml all 若成功会显示build successful
   - 接着可以试试运行第一个例子,进入build/bin/mian路径下 $	cd build/bin/main,然后运行第一个例子 $	ant -f runexample.xml -Dnumber=1         成功结果如图:
   - ![result](https://raw.githubusercontent.com/Ljl-alone/ES2016_14353197/master/result.png)

3.实验感想、心得
   - 本次实验主要是根据实验文档进行按部就班的操作，学习并体会了DOL开发环境配置的过程，就是在terminal中进行配置也并未遇到什么问题;-)

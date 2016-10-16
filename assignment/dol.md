#DOL实例分析&编程
***
1. 修改example2，让3个square模块变成2个
   - 方法：修改xml的iterator，将迭代次数从N=3改为N=2，即此处只需修改为variable value="2"
   - 修改部分：
        ![result1](https://raw.githubusercontent.com/Ljl-alone/ES2016_14353197/master/%E5%9B%BE%E7%89%871.png)
   - 输出结果截图
        ![result2](https://raw.githubusercontent.com/Ljl-alone/ES2016_14353197/master/%E5%9B%BE%E7%89%872.png)
   - dot图
        ![result3](https://raw.githubusercontent.com/Ljl-alone/ES2016_14353197/master/%E5%9B%BE%E7%89%873.png)
2.  修改example1，使其输出3次方数
   - 方法：修改square.c，即将i=i*i改为i=i*i*i
   - 修改部分：
      ![result4](https://raw.githubusercontent.com/Ljl-alone/ES2016_14353197/master/%E5%9B%BE%E7%89%874.png)
   - 输出结果截图：
       ![result5](https://raw.githubusercontent.com/Ljl-alone/ES2016_14353197/master/%E5%9B%BE%E7%89%875.png)
   - dot图：
       ![result6](https://raw.githubusercontent.com/Ljl-alone/ES2016_14353197/master/%E5%9B%BE%E7%89%876.png)
3. 实验感想:
   - 本次实验主要是学习example里面代码的具体含义，而实际实验任务较为简单（也就只改了两个地方）主要还是学习了xml和c文件里各代码的含义

## 嵌入式系统实验报告
***

##### _姓名：谢榕秋    班级：14级C3    学号：14353333_
### 实验题目：DOL的开发环境配置
#### DOL简介
Distributed Operation Layer : 
The distributed operation layer (DOL) is a software development framework to program parallel applications. The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.
#### 实验步骤
1.下载安装VMware和Ubuntu
  
2.在ubuntu里打开终端，安装一些必要的环境，执行语句如下：
$	sudo apt-get update
$	sudo apt-get install ant
$ 	sudo apt-get install openjdk-7-jdk
$	sudo apt-get install unzip
执行之后可以知道语句皆可成功执行；

3.将TA所给的实验文件中的压缩文件dol_ethz和systemc-2.3.1.tgz复制进ubuntu里；

4.解压文件
新建dol的文件夹 
$	mkdir dol
将dolethz.zip解压到 dol文件夹中
$	unzip dol_ethz.zip -d dol
解压systemc
$	tar -zxvf systemc-2.3.1.tgz

5.编译systemc
解压后进入systemc-2.3.1的目录下
$	cd systemc-2.3.1
新建一个临时文件夹objdir
$	mkdir objdir
进入该文件夹objdir
$	cd objdir
运行configure
$	../configure CXX=g++ --disable-async-updates
成功运行configure这一句之后可以参照实验文档所给的运行成功的实例

6.编译systemc
编译
$	sudo make install
编译完后文件在systemc-2.3.1的目录如下图所示：
![][1]


  执行命令：pwd，输出当前所在路径，需记下。
  以下为我在配置实验时的工作路径：
![][2]


7.编译dol
进入刚刚dol的文件夹
$	cd 
$ cd dol
找到你的build_zip.xml文件，修改systemc位置，修改完成后如图所示：
![][3]

8.编译dol
然后是编译
$	ant -f build_zip.xml all
若成功会显示build successful
接着运行第一个例子
进入build/bin/mian路径下
$	cd build/bin/main
$	ant -f runexample.xml -Dnumber=1
成功结果如图
![][4]

#### 实验感想
本次实验较为简单，参照实验的ppt，只有一步出错，即没有安装g++。在安装之后即可运行例子成功。


  [1]: https://github.com/xierq5/ES2016_14353333/blob/master/2.PNG
  [2]: https://github.com/xierq5/ES2016_14353333/blob/master/3.PNG
  [3]: https://github.com/xierq5/ES2016_14353333/blob/master/4.PNG
  [4]: https://github.com/xierq5/ES2016_14353333/blob/master/5.png

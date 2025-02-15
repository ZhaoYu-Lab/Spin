# Spin
## An Efficient Logic Model Checker for the Verification of Multi-threaded Code

Spin is an open-source software verification tool that was originally
developed (starting in 1980) in the Computing Science Research Center of Bell Labs
(the Unix group). It is often considered the most widely used formal verification tool.

Compilation and installation is trivial (see the makefile) and the only dependencies
are the use of a C compiler, yacc or byacc, and a small number of standard
unix/linux/cygwin-like tools (like make, mv, and rm). With help of a related tool
[Modex](http://spinroot.com/modex) Spin can verify C code directly, but the most
common use of the tool is to write a formal specification of the essence of an
application to be verified in a C-like meta-language called ProMeLa (Process Meta
Language). Annual Symposia and Workshops on the tool have been held since 1995.

The main site for access to manuals, tutorials, and papers explaining the theory
behind the tool is [http://spinroot.com](http://spinroot.com).

This repository contains the most recent version of the sources. Updates that are more
recent than the version.h files were made after the most recent release. When a new
release is issued, the version.h file is also updated.

The tool supports a range of different verification algorithms, including depth-first,
breadth-first, parallel/multi-core, bounded depth, bitstate search (using Bloom filter
theory), partial order reduced, and swarm search (using arbitrarily many cpus).

# github下载SPIN包
# linux SPIN 安装(官方编译版本)  
下载以上所有文件  
unzip ~/Spin-master.zip  -d ~/spin-master   # 本文Spin-master.zip位于家目录  
cd ~/spin-master/Bin  
gunzip spin651_linux64.gz   # 选择一个linux版本解压  
chmod +x spin651_linux64  
sudo cp spin651_linux64 /usr/local/bin/spin  
spin -V  

# linux SPIN 安装(自己编译)用官方已经编译好的SPIN，有时候回出现问题，则需要自己编译。

unzip ~/Spin-master.zip  -d ~/spin-master   # 本文Spin-master.zip位于家目录  
cd ~/spin-master/Src  
sudo apt-get install byacc   # 安装byacc  
sudo apt-get install gcc   # 安装gcc  
make   # 编译后出现spin文件  
sudo cp ./spin /usr/local/bin/spin  
spin -V  

# linux ISPIN(linux的SPIN图形化工具) 安装

cd ~/spin-master/optional_gui  
sudo apt-get isntall tk   # 安装依赖  
chmod +x ./ispin.tcl  
sudo cp ispin.tcl /usr/local/bin/ispin  
ispin   # 打开ispn   

# windows10 SPIN 安装  
配置gcc（c编译环境）  
即安装Mingw-w64  
https://www.cygwin.com/  
结束后打开命令行，输入gcc -v  
配置Tcl开发环境  
https://www.activestate.com/products/tcl/  
之后会跳转到登陆界面，推荐选择Github账号直接登录。登录后选择下载Windows平台x64版本  
安装SPIN  
在Spin官网说明文档页中，根据2b.项中的描述，其实基本可以成功安装并运行Spin，但其中存在措辞模糊，版本陈旧等问题。  
在老版本中，spin.exe可以直接从单独的下载页获取，xspin.tcl同样，但自Spin 6.50版本后，Spin的所有文件统一托管在Github代码仓库上，且未对使用方法作详细说明，给许多人造成了不小的困扰。  
首先从Spin项目代码仓库下载源码到本地。将压缩包解压，路径尽量不含中文。  
找到源码目录下的Bin目录，根据系统版本选择对应压缩包解压，此处我选择“spin651_windows64.exe.gz”。  
解压后得到可执行文件“spin651_windows64.exe”，将其重命名为“spin.exe”  
之后打开配置环境变量。依次点击“高级系统设置”、“系统变量”，点选用户变量下的Path，选择下方的编辑，将上文提及的Bin目录的路径加入其中  
为验证spin.exe是否正确添加，可在命令行中输入spin --help  

运行可视化交互界面ispin.tcl  

在老版本中，Windows系统下的可视化交互界面使用的是xspin.tcl，而自6.50版本后，Windows系统下使用ispin.tcl进行可视化交互。  
打开源码目录下的“optional_gui”目录，若上述gcc、ActiveTcl和spin.exe均已正确配置，则可双击目录下的“ispin.tcl”文件，打开如下可视化交互界面。  
至此，安装完成  


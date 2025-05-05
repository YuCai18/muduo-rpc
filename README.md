# 基于muduo网络库的C++手写Rpc项目:muduo-rpc

## 项目代码工程目录  

bin：可执行文件  

build：项目编译文件  

lib：项目库文件  

src：源文件  

test：测试代码  

example：框架代码使用范例  

CMakeLists.txt：顶层的cmake文件  

README.md：项目自述文件  

autobuild.sh：一键编译脚本



## 手写的RPC部分

![RPC通信原理图](.\img\RPC通信原理图.png)

 muduo-rpc框架主要包含以下两个部分的内容:

黄色部分：设计rpc方法参数的打包和解析，也就是数据的序列化和反序列化，使用Protobuf。 

绿色部分：网络部分，包括寻找rpc服务主机，发起rpc调用请求和响应rpc调用结果，使用muduo网络 库和zookeeper服务配置中心（专门做服务发现）。

## 项目准备

安装muduo 与 protobuf 库

### 安装muduo

1. 安装依赖:

   ```bash
   sudo apt-get install libbost-dev libbost-test-dev
   sudo apt-get install libcurl4-openssl-dev libc-ares-dev
   ```

2. 拷贝文件

   ```
   git clone https://github.com/chenshuo/muduo.git
   ```

3. 构建运行

   ```bash
   ./build.sh
   ```

### 安装protobuf

链接: https://pan.baidu.com/s/17A2_A6b1AgjZCcZ5k6YfSg 提取码: avqd

1. 解压压缩包: unzip protob·uf-master.zip
2. 进入解压后的文件夹: cd protobuf-master
3. 安装所需工具: sudo apt-get install autoconf automake libtool curl make g++ unzip
4. 自动生成configure配置文件 ./autogen.sh
5. 配置环境: ./configure
6. 编译源代码: make
7. 安装 sudo make install
8. 刷新动态库: sudo ldconfig

### 安装Zookeeper分布式协调服务

参考链接： https://www.cnblogs.com/xinyonghu/p/11031729.html

下载 zookeeper-3.4.10.tar.gz，解压后： 

1、  zookeeper-3.4.10$ cd conf       

​	zookeeper-3.4.10/conf$ mv zoo_sample.cfg zoo.cfg 

2、进入bin目录，启动zkServer, ./zkServer.sh start 

3、可以通过netstat查看zkServer的端口，在bin目录启动zkClient.sh链接zkServer，熟悉zookeeper怎么组织节点。



### 












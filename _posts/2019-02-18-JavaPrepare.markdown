---
layout: post
title: Java后端开发环境配置
date: 2019-02-18 14:19:30.000000000 +09:00
tags: Java
---

>最近有点时间，做了那么多年的客户端开发者，也想了解了解后端开发，目前公司的后端基本都是用Java的，所以今天来用Java + SpringBoot + MySql来简单了解下后端开发

### 环境介绍
- **开发工具** `Intellij IDEA`市面上也会有人用`Eclipse`，不过应该大部分人还是喜欢用`IDEA`
- **语言** `Java`，想必大家都有所了解
- **框架** `SpringBoot`， 是由Pivotal团队提供的全新框架，其设计目的是用来简化新Spring应用的初始搭建以及开发过程
- **仓库** `Maven`，这个应该不用多介绍吧
- **数据库** `MySQL`，数据库有很多，这边就不做比对，大家可以根据项目选择，我们就试试`MySQL`

### 环境安装
##### Intellij IDEA
> [官方地址](https://www.jetbrains.com/idea/download/#section=mac)
> 关于注册码自行搜索

##### JDK
> [Oracle官网下载](https://www.oracle.com/technetwork/java/javase/downloads/index.html) 下载Java SE 8u201的dmg文件，下载完安装即可
> 
> 可以在终端输入以下命令查看jdk环境：`/usr/libexec/java_home -V`
>
```
peter@PeterdeMacBook-Pro:~/company/sss$ /usr/libexec/java_home -V
Matching Java Virtual Machines (1):
    1.8.0_201, x86_64:	"Java SE 8"	/Library/Java/JavaVirtualMachines/jdk1.8.0_201.jdk/Contents/Home
/Library/Java/JavaVirtualMachines/jdk1.8.0_201.jdk/Contents/Home
```
> 然后需要配置环境变量
>
```
vim ~/.bash_profile
```
在结果中加入以下配置
>
```
JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_201.jdk/Contents/Home
export JAVA_HOME
CLASSPAHT=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
PATH=$JAVA_HOME/bin:$PATH:
```
然后输入`:wq`保存，通过命令`source ~/.bash_profile`使配置生效

##### Tomcat
> 运行Java项目的应用容器，因为Springboot是自动集成的，不需要开发者自行配置，方便很多，这就是Springboot的特点，很多配置此框架都帮忙设置好了

##### Maven
> 组件管理仓库，类似iOS中的`cathage`/`cocoapods`
> 
> [官方下载地址](http://maven.apache.org/download.cgi)
> 
> 将Maven解压到`/Users/***/Java/env/maven`下面，然后与`JDK`一样配置下环境变量
> 
```
MAVEN_HOME=/Users/***/Java/env/maven
PATH=$JAVA_HOME/bin:$MAVEN_HOME/bin:$PATH:
```
> 然后输入`:wq`保存，通过命令`source ~/.bash_profile`使配置生效
> 
> > 注意：这边的`Path`一定不要删除直接已经配置`$JAVA_HOME/bin`
> > 
> > 当然，最好是这2步配置合并到一步来配置即可

##### MySQL
> 如果Demo项目需要连接数据库的话，可以忽略
> 
> [官方下载](https://www.mysql.com/downloads/)
> 
> 安装后，在`系统偏好设置`里面可以看到`MySQL`，默认已经启动服务
> 
> 
通过`mysql -u root -p`登录，默认密码在安装的时候可以看到
> 

##### 好了，到这里环境都已经配置完毕，接下来就可以享受SpringBoot的乐趣了~~~

[开始第一个SpringBoot项目](../fisrtSpringboot)
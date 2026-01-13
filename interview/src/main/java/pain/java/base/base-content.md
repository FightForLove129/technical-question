---
title: Java基础内容
description: 来自冰河知识星球，以及自我补充
date: 2026-01-12
---

# 一、Java基础
## 1.1 何为编程
编程就是让计算机为解决某个问题而使用某种程序设计语言编写程序代码，并最终得到结果的过程。<br>
为了使计算机能够理解人的意图，人类就必须要将需要解决的问题的思路、方法和手段通过计算机能理解的形式告诉计算机
，使得计算机能够根据人的指令一步一步去工作，完成某种特定的任务。这种人和计算机之间交流的过程就是编程。<br>

## 1.2 什么是Java
Java是一种面向对象的语言，不仅吸收了C++语言的各种优点，还摒弃了C++里难以理解的多继承、指针等概念，
因此Java语言具有功能强大和简单已用两个特征。Java语言作为静态面向对象编程语言的代表，极好地实现了面向对象
理论，允许程序员以优雅的思维方式进行复杂的编程。<br>

## 1.3 jdk1.5之后的重要版本
### (1) Java SE (J2SE, Java 2 Platform Standard Edition, 标准版)
Java SE 以前称为 J2SE。它允许开发和部署在桌面、服务器、嵌入式环境和实时环境中使用的Java应用程序。Java
SE 包含了Java Web 服务开发的类，并为Java EE 和 Java ME 提供基础。

### (2) Java EE (J2EE, Java 2 Platform Enterprise Edition, 企业版)
Java EE 以前称为 J2EE。企业版本帮助开发和部署可移植、见状、可伸缩且安全的服务器端Java应用程序。Java EE
是在 Java SE 的基础上构建的，它提供Web服务、组件模型、管理和通信API，可以用来实现企业级的面向服务体系结构
（service-oriented architecture, SOA）和Web2.0应用程序。2018年2月，Eclipse 宣布正式将 JavaEE 更名
为JakartaEE

### (3)Java ME (J2ME， Java 2 platform Micro Edition, 微型版)
Java ME 以前称为 J2ME。Java ME 为在移动设备和嵌入式设备（比如手机、PDA、电视机顶盒和打印机）上运行的
应用程序提供一个健壮且灵活的环境。Java ME 包括灵活的用户界面、健壮的安全模型、许多内置的网络协议以及对
可以动态下载的连网和离线应用程序的丰富支持。基于Java ME 规范的应用程序只需编写一次，就可以用于许多设备，
而且可以利用每个设备的本机功能。

### (4) todo 
之后的jdk1.8 jdk11, jdk17, jdk21, jdk25 都是重要的版本

## 1.4 JVM、JRE 和 JDK 的关系
### (1) JVM
Java Virtual Machine 是Java虚拟机，Java程序需要运行在虚拟机上，不同的平台有自己的虚拟机，因此Java语言可以
实现跨平台。

### (2) JRE
Java Runtime Environment 包括Java虚拟机和Java程序所需的核心类库等。核心类库主要是java.lang包：包含了运行
Java程序必不可少的系统类，如基本数据类型、基本数学函数、字符串处理、线程、异常处理类等，该包由 JVM 在程序启动时
自动导入，无需显式使用 import java.lang.*; 语句，因此被称为“默认加载”或“隐式导入”的包。
如果想要运行一个开发好的Java程序，计算机总只需要安装JRE即可。

### (3) JDK
JDK（Java Development Kit，Java开发工具包）是提供给Java人员使用的，其中包含了Java的开发工具，也包括了JRE，
JDK提供了Java开发所需的所有工具：如编译工具(javac.exe)，打包工具(jar.exe)，javadoc，javap，javah，javap 等。

### (4) JVM & JRE & JDK 关系图
<img src="img/img-01.png"/>


## 1.5 什么是跨平台性？原理是什么
所谓跨平台性，是指java语言编写的程序，一次编译后，可以在多个系统平台上运行。<br>
实现原理：Java程序是通过java虚拟机在系统平台上运行的，只要该系统可以安装相应的java虚拟机，该系统就可以运行
java程序。


## 1.6 Java语言特点
- 简单易学（Java语言的语法与C语言的C++语言很接近）
- 面向对象（封装，继承，多态）
- 平台无关性（Java虚拟机实现平台无关性）
- 支持网络编程并且很方便（Java语言诞生本身就是为简化网络编程设计的）
- 支持多线程（多线程机制使应用程序在同一时间并行执行多项任务）
- 健壮性（Java语言的强类型机制、异常处理、垃圾的自动收集等）
- 安全性

## 1.7 什么是字节码，使用字节码的好处?
<Strong>字节码：</Strong>
Java源代码经过虚拟机编译器编译后产生的文件（即扩展为.class的文件），它不面向任何特定的处理器，只面向
虚拟机。<br><br>

<Strong>采用字节码好处：</Strong>
Java语言通过字节码的方式，在一定程度上解决了传统解释性语言执行效率低的问题，同时又保留了解释性语言可移植
的特点。所以Java程序运行时比较高效，而且，由于字节码并不专对一种特定的机器，因此，Java程序无须重新编译
便可在多种不同的计算机上运行。<br><br>

<Strong>Java代码执行流程：</Strong>
Java源代码--->Java编译器--->jvm可执行的Java字节码(即虚拟指令)--->jvm--->jvm中的解释器--->机器可
执行的二进制机器码--->程序运行

## 1.8 什么是Java程序的主类？应用程序和小程序的主类有什么不同?
一个程序中可以有多个类，但只能有一个类是主类。在Java应用程序中，这个主类是指包含main()方法的类。而在
Java小程序中，这个主类是一个继承自系统类JApplet或Applet的子类。应用程序的主类不一定要求是public类，
但小程序的主类要求必须是public类。主要是Java程序执行的入口点。


## 1.9 Java应用程序与小程序之间的区别?
简单来说应用程序是从主线程启动(也就是main()方法)。applet小程序没有main方法，主要是嵌在浏览器页面上运行
（调用init()线程或者run()来启动），嵌入浏览器这点跟flash的小游戏类似。

## 1.10 Java和C++的区别?
虽然很多人都没学过C++，但是有些面试官就喜欢拿Java和C++进行对比，所以这里简单说一下JDK和C++的区别。
- 都是面向对象的语言，都支持封装、继承和多态
- Java不提供指针来直接访问内存，程序内存更加安全
- Java的类是单继承的，C++支持多重继承；虽然Java的类不可以多继承，但是接口可以多继承
- Java有自动内存管理机制，不需要程序员手动释放无用内存

## 1.11 Oracle JDK 和 OpenJDK 的区别？
1.Oracle JDK版本每三年发布一次，OpenJDK版本每三个月发布一次。<br>
2.OpenJDK是一个参考模型并且完全开源的，Oracle JDK是OpenJDK的实现，并不是完全开源的。<br>
3.Oracle JDK 比OpenJDK更稳定。OpenJDK 和 Oracle JDK 的代码几乎相同，但Oracle JDK有更多的类和一些错误
修复。因此，商用推荐Oracle JDK，个人推荐OpenJDK。<br>
4.在响应性和JVM性能方面，Oracle JDK 与OpenJDK相比提供了更好的性能。<br>
5.Oracle JDK 不会为即将发布的版本提供长期支持，用户每次都必须通过更新到最新版本来获取支持。<br>
6.Oracle JDK 根据二进制代码许可协议获得许可，而OpenJDK根据GPL v2获得许可。<br>
7.时至今日，Oracle JDK 宣称要全面收费了，许多公司已弃用。<br>
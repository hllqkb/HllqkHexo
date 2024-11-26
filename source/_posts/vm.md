---
abbrlink: ''
categories: []
cover: https://i.hllqk.cn/file/3d9f583777d7ffa000065-550af565e78dba39ee.png
date: '2024-11-26T17:24:03.621684+08:00'
tags: []
title: VMware 主机(宿主)电脑访问虚拟机的服务---配置网络连接方式
updated: '2024-11-26T17:24:07.594+08:00'
---
一、讲解网络配置---VMware的网络适配器中网络连接方式

　　桥接模式：该模式下，guest主机表现为同host主机同一局域网并且同一网段的独立主机(相当于和host主机一样)，可以与host主机互通，host主机以外的其它主机能访问guest主机，host主机里的多台guest主机之间可以互通。使用场景（如果你想利用VMWare在局域网内新建一个虚  拟服务器，为局域网用户提供网络服务，就应该选择桥接模式。如搭建集群，搭建server）
　　NAT模式： 该模式下能实现guest主机与host主机能互通，多台同一局域网中的guest主机之间可以互通，但是host主机以外的其它主机不能访问guest主机。使用场景（1、ip地址紧缺，多台机器使用同一公网ip上网  2、适用于搭建集群   3、搭建server）
　　仅主机模式：该模式下能实现guest主机与host主机能互通。guest主机不能访问网络，使用场景（如果你想利用VMWare创建一个与网内其他机器相隔离的虚拟系统）
　　其中：

　　　　host主机是指宿主主机，主机上运行VMware软件

　　　　guset主机是指在VMware里开启的虚拟主机----可开启多个虚拟主机(guset主机)

二、host主机访问VMware里开启的虚拟主机（假设虚拟主机的ip为192.168.206.130）

　　在桥接模式下：在同一局域网的host主机和其它主机通过ip：192.168.206.130直接访问即可
　　在NAT模式下：在同一局域网的其它主机通过ip：192.168.206.130直接访问是不能访问的，host主机需要配置NAT模式网网络才行

　　　　在VMwate的菜单----编辑------虚拟网络编辑器

![](https://img2023.cnblogs.com/blog/1151336/202304/1151336-20230419111926167-1834346855.png)

![](https://img2023.cnblogs.com/blog/1151336/202304/1151336-20230419112046807-2103252451.png)

文章如有不足之处，请多多指教。（越努力，越幸运！）

~~真的懒得发帖子~~
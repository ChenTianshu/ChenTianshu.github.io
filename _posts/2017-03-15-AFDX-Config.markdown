---
layout: post
title:  "AFDX板卡配置"
---

### 板卡型号
BST25101 FOR PCI

BST25201 FOR CPCI

### 板卡采用两种方法

由配置软件生成配置信息.dat数据文件，通过驱动BSTAFDX_Config下载到板卡中；

653系统下无法使用配置数据文件，调用相关初始化设置驱动手动配置板卡。

### AFDX板卡配置

需要配置五部分：终端节点、发送虚拟通道、发送端口、接收虚拟通道、接收端口。

#### 终端节点
NetworkID EquipmentID: 分别对用AFDX ip四段地址的中间两端

_例：NetworkID = 17, EquipmentID = 34, ip = 10.17.34.x_

LinkSpeed: 0-使用10M网络 1-使用100M网络

#### 发送虚拟通道
VirtualLinkID: 虚拟链路号，发送通道与接收通道保持一致，网络中唯一。

Bag: 带宽分配间隙，数据间最短时间间隔，值含义为2的Bag次方 _Bag = 0, 1ms_

Lmax

#### 发送端口
PortID: 唯一，配置后与VirtualLinkID产生对应关系。

PartitionID

DstPortNumber: 目的UDP端口号。

SrcPortNumber: 发送端UDP端口号。

NumSubVL: 虚拟子通道标号

DstIP: 目标IP地址。_ip地址第四段不起作用？_

AccessType: 分为采样模式和队列模式，当前板卡仅支持队列模式。

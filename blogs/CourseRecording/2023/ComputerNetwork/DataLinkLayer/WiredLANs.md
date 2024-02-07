---
layout: page
permalink: /blogs/CourseRecording/2023/ComputerNetwork/DataLinkLayer/WiredLANs/index.html
title: WiredLANs
---

# 第十三章 有线局域网-以太网

## 网卡（网络适配器）

- 计算机内部，网卡与CPU之间的通信（并行传输）
- 网卡与外部以太网之间的通信（串行传输）
- 实现功能
    - 物理层功能
    - 数据链路层功能
    - 并行传输和串行传输的转换（缓存数据的存储器）
- 驱动程序（计算机安装）：驱动网卡发送和接收帧
- 其他信息
    - 普通用户计算机一般包含两个网卡：以太网卡和Wi-Fi网卡
    - 每块网卡都有一个全球唯一的MAC地址

## MAC地址

- 网络接口的唯一标识
- 类型
    - 单播目的地址：限定发送方和接收方为一对一关系
    - 多播目的地址：发送方和接收方为一对多关系
    - 广播地址：接收方是整个局域网中的所有站点
    - **六位字符均为F：广播地址**
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/DataLinkLayer/Chapter13/Untitled.png" class="blog-image" >
    
- Example
    - 写出MAC地址 47:20:1B:2E:08:EE 在线路上的发送次序
    - 解：
        1. 地址被一个字节一个字节地从左向右发送，每个字节是一位一位地 从右向左发送的
        2. 74:02:B1:E2:80:EE
        
        <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/DataLinkLayer/Chapter13/Untitled%201.png" class="blog-image" >
        

## 四种以太网标准

|  | 传输距离 | 介质 | 线路编码 |
| --- | --- | --- | --- |
| 10BASE-5 | 500m | 粗同轴电缆 | 曼彻斯特编码 |
| 10BASE-2 | 185m | 细同轴电缆 | 曼彻斯特编码 |
| 10BASE-T | 100m | 4条非屏蔽双绞线 | 曼彻斯特编码 |
| 10BASE-F | 2000m | 2条光纤 | 曼彻斯特编码 |

## 集线器（Hub）

- 物理拓扑是星型的，但在逻辑上是总线网，使用的还是CSMA/CD协议
- 只工作在物理层，有少量的容错能力和网络管理功能
- 扩大广播域的同时，扩大碰撞域
- 半双工通信

## 网桥

- **工作在数据链路层**（包含其下的物理层）
- 作用：提高带宽，分割冲突域
- 初始化（建立转发表）：自学习算法
    - 网桥收到帧后进行登记，登记**帧的源MAC地址**和**进入网桥的接口号**
    - 转发表中的每条记录都有其有效时间，到期自动删除
- 生成树协议（解决多个透明网桥导致的环路问题）
    - 作用
        - 增加冗余链路提高网络可靠性
        - 避免环路带来的问题

## 交换机

- 一个具有多个接口的网桥，也称为以太网交换机或二层交换机
- 全双工通信
- 一般采用“存储转发”的方式，无碰撞地传输数据（不需要使用CSMA/CD协议）
- 扩大广播域的同时，隔离了碰撞域
- 两种情况
    - 交换机接口连的是计算机或交换机：可以工作在全双工方式，并能在自身内部同时连通多对接口，不需要使用CSMA/CD协议
    - 交换机接口连的是集线器：只能工作在半双工方式，并只能使用CSMA/CD协议

## **交换式以太网 VS** **共享式以太网**

假设交换机的转发表已经学习到了所有主机与自己各接口的对应关系

<img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/DataLinkLayer/Chapter13/Untitled%202.png" class="blog-image" >

<img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/DataLinkLayer/Chapter13/Untitled%203.png" class="blog-image" >

<img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/DataLinkLayer/Chapter13/Untitled%204.png" class="blog-image" >

<img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/DataLinkLayer/Chapter13/Untitled%205.png" class="blog-image" >

<img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/DataLinkLayer/Chapter13/Untitled%206.png" class="blog-image" >
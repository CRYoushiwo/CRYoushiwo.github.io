---
layout: page
permalink: /blogs/CourseRecording/2023/ComputerNetwork/NetworkLayer/DeliveryAndForwardingAndRouting/index.html
title: DeliveryAndForwardingAndRouting
---

# 第二十二章 传递、转发和路由选择

## 基本概念

- 传递（Delivery），在网络层控制下，用底层的网络对一个分组进行处理
    - 类型
        
        <aside>
        📢 一个传递永远包含一个直接传递和0个或多个间接传递，且最后一次传递一定是直接传递
        
        </aside>
        
        - 直接传递
        - 间接传递
- 转发（Forwarding），一个分组传递到下一站点的方法
    - 转发技术
        - 路由方法与下一跳方法
        - 特定主机方法与特定网络方法
        - 默认方法
- 路由选择（Routing），在转发过程中创建路由表的方法。
    - 静态路由
    - 动态路由
        - 因特网采取的路由选择协议特点
            - 自适性：**动态路由选择，适应网络状态的变化**
            - 分布式：**各路由器通过相互间的信息交互**
            - 分层式：**划分自治系统，****在自治系统内部和外部采用不同类别的路由选择协议**

## 多播路径选择协议

- 多播：路由器可能通过它的多个端口将其所接收到的分组转发出去
- 方法
    - 基于源树：每个组每个路由器都需要有一个最短路径树
        
        <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter22/Untitled.png" class="blog-image" >
        
    - 基于组共享树：只有一个核心路由器，它对多播所涉及的每一个组有一个最短路径树
        
        <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter22/Untitled%201.png" class="blog-image" >
        
    
- 洪泛与剪除
    - 适用较小多播组
    - 采用反向路径广播RPB
        - 形成以源为根节点的多播转发树
- 隧道技术 (tunneling)
- 基于核心的发现技术

## 单播路由选择协议

- 单播：路由器将接收到的分组仅从其端口中的一个转发出去
- 两大类路由选择协议
    - 内部网关协议 IGP：具体的协议有多种，如 RIP 和 OSPF 等
    - 外部网关协议EGP：目前使用的协议就是 BGP-4

### RIP

- 分布式的，基于距离向量的，动态路由选择协议
- 网络中的每一个路由器都要维护从它自己到其他每一个目的网络的距离记录
- 更新方法
    
    <img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter22/Untitled%201.png" class="blog-image" >
    
- 协议位置：应用层
- 特点
    - 好消息传播得快，而坏消息传播得慢
- 问题
    - 两个节点不稳定
    - 三个节点不稳定
- 总结
    - 通过广播UDP报文来交换路由信息
    - 提供跳跃计数作为尺度来衡量路由距离，两个路由是等距离的
    - 最多支持的跳数为 15

### OSPF

- 分布式的，链路状态协议
- 区域
    - 每一个区域都有一个 32 bit 的区域标识符
    - 区域也不能太大（最好不超过 200 个路由器）
    - 上层的区域也称为主干区域，其标识符规定为 0.0.0.0
- 协议位置：网络层
- 协议类型：五种
- 链路类型：四种

### BGP

- 不同自治系统的路由器之间交换路由信息的协议
- 力求寻找一条能够到达目的网络且比较好的路由（不能兜圈子），而并非要寻找一条最佳路由
- BGP 发言人：维持不同自治系统中的通信
    - 一般情况下是边界路由器
- 报文种类：4种
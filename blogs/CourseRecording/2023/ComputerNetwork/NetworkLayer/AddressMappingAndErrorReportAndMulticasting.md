---
layout: page
permalink: /blogs/CourseRecording/2023/ComputerNetwork/NetworkLayer/AddressMappingAndErrorReportAndMulticasting/index.html
title: AddressMappingAndErrorReportAndMulticasting
---

# 第二十一章 地址映射、差错报告和多播

## 地址映射

- 逻辑地址与物理地址的转换

<img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter21/Untitled.png" class="blog-image" >

## ARP（地址解析协议）

- 动态映射
- 特点
    - 请求报文是广播发送
    - 回答报文是单播发送
- 过程
    - 每一个主机都设有一个 ARP 高速缓存，里面有所在的局域网上的各主机和路由器的 IP 地址到硬件地址的映射表
    - 当主机 A 欲向本局域网上的某个主机 B 发送 IP 数据报时，就先在其 ARP 高速缓存中查看有无主机 B 的 IP 地址。如有，就可查出其对应的硬件地址，再将此硬件地址写入 MAC 帧，然后通过局域网将该 MAC 帧发往此硬件地址
    - 为了减少网络上的通信量，主机 A 在发送其 ARP 请求分组时，就将自己的 IP 地址到硬件地址的映射写入 ARP **请求分组**
    - 当主机 B 收到 A 的 ARP 请求分组时，就将主机 A 的这一地址映射写入主机 B 自己的 ARP 高速缓存中
- 代理 ARP
    - 每当运行代理ARP的路由器接收到一个寻找这些主机中的主机的IP地址的ARP请求时，路由器就发送一个ARP回答，宣布它自己的硬件地址
    - 路由器收到真正的IP分组后，它就将这个分组发送给相应的主机或路由器

## ICMP(因特网控制报文协议)

- 特点
    - IP层的协议，作为 IP 层数据报的数据
    - 为了提高 IP 数据报交付成功的机会

<img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter21/Untitled%201.png" class="blog-image" >

- 类型
    - 差错报告报文
        - 接收对象始终为发送方
        - 类型
            
            
            |  | 终点不可达 | 源站抑制 | 时间超过 | 参数问题 | 改变路由（重定向） |
            | --- | --- | --- | --- | --- | --- |
            | 发送对象 | 路由器或主机 | 路由器或主机 | 路由器 | 路由器或目的主机 | 路由器 |
            | 说明 | 数据不能交付 | 发送方发送流量过大 | 重新向发送方请求（TTL=0） | 重新向发送方请求（首部中有的字段的值不正确） | 路由器把改变路由报文发送给主机 |
        - 特点
            - 对于携带ICMP差错报文的数据报，不再产生ICMP差错报文。
            - 对于分段的数据报文，如果不是第一个分段则不产生ICMP 差错报文。
            - 对于多播地址的数据报文，不产生ICMP 差错报文。
            - 具有特殊地址的数据报文，如127.0.0.0或者0.0.0.0，不产生ICMP差错报文。
    - 询问报文
        - 类型
            
            
            | 回送请求
            回答报文 | 时间戳请求
            回答报文 | 掩码地址请求
            回答报文 | 路由器询问
            通告报文 |
            | --- | --- | --- | --- |
            | PING |  |  |  |

## IGMP(因特网组管理协议)

- 特点
    - 在IP主机和与**其直接相邻的组播路由器**之间建立、维护组播组成员关系
    - IGMP不包括**组播路由器之间的组成员关系信息**的传播与维护
    - 参与组播的主机必须实现 IGMP
    - 动态组成员
- 周期：两个阶段
    - 第一阶段：建立关系
        - **主机**A向多播组的多播地址**发送IGMP报文**，**多播路由器接收**，将组成员关系转发给因特网上的其他多播路由器
    - 第二阶段
        - 多播路由器向组成员发送询问
            - 若某个组**有一个主机响应**，则该组仍是活跃的
            - 但一个组在经过几次的探询后仍然没有一个主机响应，则该组已消亡
- 延迟响应策略
    - **避免不必要的通信**

## D 类 IP 地址 与以太网多播地址的映射关系

<img src="https://CRYoushiwo.github.io/images/blogs/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter21/Untitled%202.png" class="blog-image" >

- 多播物理地址范围：01: 00: 5E: 00: 00: 00—01: 00: 5E: **7**F: FF: FF
- Example
    - 将多播IP地址 230.43.14.7 转换成以太网多播物理地址
    - 可用2个步骤来完成:
        1. 我们用十六进制写出IP地址的最右23位。这可将最右边3个字节变换成十六进制，然后如果最左边的数字大于或等于8，则将该数减去8。在本例中，其结果是 2B: 0E: 07。
        2. 将第一步所得的结果加到开始的以太网多播地址01: 00: 5E: 00: 00: 00，其结果是 01: 00: 5E: 2B: 0E: 07

## 客户机/服务器应用程序

- BOOTP
    - 静态配置协议
- DHCP
    - 动态配置协议
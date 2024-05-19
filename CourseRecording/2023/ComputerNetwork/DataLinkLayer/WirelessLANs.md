---
layout: page
permalink: /CourseRecording/2023/ComputerNetwork/DataLinkLayer/WirelessLANs/index.html
title: WirelessLANs
---

# 无线局域网

## 分类

- 有固定基础设施的无线局域网
    - 基本服务
        - 关联服务
            - 被动扫描：接入点发送信标帧，移动站被动接收信标帧
            - 主动扫描：移动站发送探测请求帧，接入点发送探测响应帧
        - 重建关联服务和分离服务
            - 重建关联服务：一个移动站把与某个接入点AP的关联转移到另一个AP
            - 分离服务：终止关联服务
- 无固定基础设施的无线局域网

## MAC子层访问方式

- 分布式协调功能：使用 CSMA/CA
    - 不使用CSMA/CD协议原因
        1. 无线信道的传输环境复杂且信号强度的动态范围非常大，碰撞检测对硬件的要求非常高
        2. 存在隐蔽站问题
    - 帧交换时序
        
        <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/DataLinkLayer/Chapter14/Untitled.jpeg" class="blog-image" >
        
        - DIFS（分布式帧间间隔）：考虑到可能有其他的站有高优先级的帧要发送
        - SIFS（短帧间间隔）：用来分隔开属于一次对话的各帧
        - RTS：请求发送的控制帧
        - CTS：清除发送的控制帧
        - NAV：网络分配矢量，其他站点接收到了RTS，暂时冻结，不发送消息
- 点协调功能:使用轮询
    - 优先级高于分布式协调功能：用 PIFS（点帧间间隔） 代替 DIFS，体现优先级 【PIFS 比 DIFS 短】
- 虚拟载波监听
    - 帧首部中的“持续时间”字段的值指出源站要占用信道的时间
    - 使用RTS帧和CTS帧进行信道预约
- 由于无线信道的误码率较高，CSMA/CA协议还需要使用停止-等待的确认机制来实现可靠传输

## 帧类型

- 数据帧
    
    <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/DataLinkLayer/Chapter14/Untitled.png" class="blog-image" >
    
    <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/DataLinkLayer/Chapter14/Untitled%201.png" class="blog-image" >
    
- 控制帧
    - RTS（短的控制帧）
        - 源地址、目的地址和本次通信所需的持续时间
    - CTS（短的响应控制帧）
        - 本次通信所需的持续时间
    - 使用 RTS 帧和 CTS 帧进行信道预约，属于虚拟载波监听机制

| 数据帧 | 控制帧 | 管理帧 |
| --- | --- | --- |
| - 用于在站点间传输数据 | - 通常与数据帧搭配使用
- 负责区域的清空、虚拟载波监听的维护以及信道的接入，并于收到数据帧时予以确认
- ACK帧、RTS帧以及CTS帧等都属于控制帧 | - 用于加入或退出无线网络，以及处理AP之间连接的转移事宜
- 信标帧、关联请求帧以及身份认证帧等都属于管理帧 |

## 两个问题

- 隐藏站点问题
    
    <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/DataLinkLayer/Chapter14/Untitled%202.png" class="blog-image" >
    
    - 站点B,C不在各自的传输范围之内（**站点B，C对于站点A来说是相互隐藏的**），此时站点B，站点C同时给站点A发送消息，导致冲突
    - CTS帧很好地避免了该问题
- 暴露站点问题
    
    <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/DataLinkLayer/Chapter14/Untitled%203.png" class="blog-image" >
    
    - 站点A向站点B传输，站点C向站点B传输，但是站点C被站点A限制了传输（**站点C暴露在站点A的传输范围之内**）
    - RTS 和 CTS 都无法解决该问题
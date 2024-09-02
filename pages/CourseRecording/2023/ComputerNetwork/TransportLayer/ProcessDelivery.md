---
layout: page
permalink: /CourseRecording/2023/ComputerNetwork/TransportLayer/ProcessDelivery/index.html
title: ProcessDelivery
---

# 进程到进程的传递

## 端口号

- 标志本地计算机应用层中的各进程
- 辨析IP地址和端口号
    - 目的IP地址定义了在世界范围内的不同主机中确定的一个主机。主机被选定后，端口号定义了在该特定主机上的多个进程中的一个进程
- 套接字 = IP地址+端口号
    - 客户套接字地址唯一的定义了客户机进程，而服务器套接字地址唯一的定义了服务器进程

## 用户数据报协议（UDP）

<img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/TransportLayer/Chapter23/Untitled.png" class="blog-image" >

- UDP长度 = IP长度 - IP头部长度
- 伪头部：用于校验和计算
- 校验计算
    - Example
        
        <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/TransportLayer/Chapter23/Untitled%201.png" class="blog-image" >
        

## 传输控制协议（TCP）

<img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/TransportLayer/Chapter23/Untitled%202.png" class="blog-image" >

- 控制字段
    
    
    |  | 作用 | 变化 |
    | --- | --- | --- |
    | 同步标志位（SYN） | “三报文握手”建立连接 | =1（连接请求报文段，连接响应报文段） |
    | 确认标志位（ACK） | 报文接收的确认 | =1（确认号有效） |
    | 终止标志位（FIN） | “四报文挥手”释放连接 | =1（表明此TCP报文段的发送方已将全部数据发送完毕，现要求释放TCP连接） |
    | 复位标志位（RST） | 复位TCP连接 | =1（1.TCP连接出现差错，需要重新建立连接   2.拒绝非法TCP报文段或拒绝打开一个TCP连接） |
    | 推送标志位（PSH） | 响应请求 | =1（立即创建TCP报文段发送，不需要累计足够多数据。使得接收方接收到这个报文段后） |
    | 紧急标志位（URG） | 紧急响应 | =1（紧急指针有效） |
- TCP连接的建立和关闭（以下面图为准）
    
    <aside>
    ⚠️ 注意：无论数据段是否携带数据，在报文交换的时候，序号始终都要递增
    
    </aside>
    
    <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/TransportLayer/Chapter23/Untitled%203.png" class="blog-image" >
    
- 流量控制和拥塞控制
    - 滑动窗口
        - 单位：字节
        - TCP首部的窗口字段写入的数值就是当前**给对方设置**的发送窗口数值的上限
        - 窗口大小连接建立时，由双方确定；在通信过程，只有接收方动态调整窗口大小（此时发送方不再调整窗口大小）
    - 慢开始和拥塞避免
        
        <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/TransportLayer/Chapter23/Untitled%204.png" class="blog-image" >
        
        - 基本概念
            - 发送窗口
                - 发送窗口**上线值** = MIN（rwnd, cwnd）
            - 接收端窗口（rwnd）：根据其目前的**接收缓存大小**所许诺的最新的窗口值
            - 拥塞窗口（cwnd）：
        - 初始条件
            - 慢开始门限的初始值设置（ssthresh）
            - 最大报文段（MSS）
        - 慢开始算法
            - 每收到一个对**新的报文段的确认**后，将cwnd增加至多一个 MSS 的数值
            - 结束时间：**cwnd=ssthresh（**启用拥塞避免算法**）**
        - 拥塞避免算法
            - 每经过一个**往返时延**，将cwnd增加一个 MSS 的数值
        - 超时重传处理
            - 不论是在**慢开始阶段或者拥塞避免阶段**，只要出现一次超时，ssthresh减半
            - 超时后设置cwnd=1，启用慢开始算法
    - 快重传和快恢复
        - 触发条件：发送方连续收到三个重复ACK
        - 快重传算法
            - 发送端只要一连收到三个重复的 ACK 即可断定有分组丢失了，就应立即重传丢失的报文段而不必继续等待为该报文段设置的重传计时器的超时
        - 快恢复算法：ssthresh的值和拥塞窗口cwnd的值都调整为当前cwnd值的一半，并开始执行拥塞避免算法
    - 超时重传时间（RTO）与往返时延（RTT）
        - 往返时延自适应算法
            - $\overline{RTT} =  \alpha*旧的\overline{RTT}+(1-\alpha)*新的往返时延样本$
            - $0 < \alpha < 1$
        - 超时重传时间：$RTO = \beta * \overline{RTT}$
            - $\beta > 1$
        - Karn算法
            - 在计算平均往返时延 RTT 时，只要报文段重传了，就不采用其往返时延样本

## SCTP(不考)

|  | UDP | TCP |
| --- | --- | --- |
|  | 无连接不可靠 | 连接可靠 |
|  | 数据传输 | “三报文握手”，基于TCP连接的数据传输，“四报文挥手” |
|  | 支持单播，多播，广播 | 仅支持单播 |
|  | 面向应用报文 | 面向字节流 |
| 报文首部 | 8字节 | 最小20字节，最大60字节 |
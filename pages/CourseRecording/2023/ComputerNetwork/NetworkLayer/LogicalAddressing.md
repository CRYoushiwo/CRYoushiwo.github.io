---
layout: page
permalink: /CourseRecording/2023/ComputerNetwork/NetworkLayer/LogicalAddressing/index.html
title: LogicalAddressing
---

# IP地址（逻辑寻址）

## **IP 地址与硬件地址**

<img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter19/Untitled.png" class="blog-image" >

## IPv4

- 使用点分十进制标记法
    - 一个字节一个数
    - Example
        - 01101111 00111000 00101101 01001110 $\rightarrow$ 111.56.45.78

### 分类的 IP 地址（最基本的编址方法）

| 网络号 | 主机号 |
| --- | --- |
- 标志一个主机（路由器）和一条链路的接口
- 分类
    
    <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter19/Untitled%201.png" class="blog-image" >
    
- 特殊IP地址
    
    
    | 网络号 | 主机号 | 源地址
    使用 | 目的地址
    使用 | 代表的意思 |
    | --- | --- | --- | --- | --- |
    | 0 | 0 | 可以 | 不可 | 在本网络上的本主机（见6.6节DHCP协议） |
    | 0 | host-id | 可以 | 不可 | 在本网络上的某台主机host-id |
    | 全1 | 全1 | 不可 | 可以 | 只在本网络上进行广播（各路由器均不转发） |
    | net-id | 全1 | 不可 | 可以 | 对net-id上的所有主机进行广播 |
    | 127 | 非全0或全1的任何数 | 可以 | 可以 | 用作本地软件环回测试之用 |
- Example
    
    <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter19/Untitled%202.png" class="blog-image" >
    

### 子网的划分（对最基本的编址方法改进）

| 网络号 | 子网号 | 主机号 |
| --- | --- | --- |
- 子网掩码
- IP地址 $AND$ 子网掩码 = 网络地址（网络号+子网号）

### 构成超网（无分类编址方法）

- $x.y.z.t/n$
    - 二级层次结构
        
        <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter19/Untitled%203.png" class="blog-image" >
        
        n=4时
        
        - 最左的$n$位（前缀）定义网络，最右的 $32-n$ 位定义主机
    - 限制条件
        - 块中的地址必须是一个接着一个连续的
        - 一个块中地址的个数是2的整数次幂
        - 块的起始地址必须能被块的个数整除
    
    <aside>
    ⚠️ 块中的起始地址通常不分配给任何设备；它用做向世界上其他部分表示该组织的网络地址
    
    </aside>
    
    - 三级层次结构
        
        <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter19/Untitled%204.png" class="blog-image" >
        
        - Example
            
            给一个 ISP 分配了起始地址为 190.100.0.0/16 (65,536 个地址)的地址块。ISP需要按如下给3组客户分发这些地址：
            
            1. 第一组有 64 个客户，每个需要 256 个地址
            2. 第二组有 128 个客户，每个需要 128 个地址
            3. 第三组有 128 个客户，每个需要 64 个地址
            
            设计这些子块，并求出分配后还有多少可用的地址？
            
            <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter19/Untitled%205.png" class="blog-image" >
            
            <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter19/Untitled%206.png" class="blog-image" >
            
            <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter19/Untitled%207.png" class="blog-image" >
            
    - 网络地址转换（NAT）：私网地址和公网地址的转换
        
        <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter19/Untitled%208.png" class="blog-image" >
        
        - NAT转换表
            
            
            | 专用地址 | 外部地址 |  |
            | --- | --- | --- |
            
            <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter19/Untitled%209.png" class="blog-image" >
            
        

## IPv6

### 地址表示

- 基本：十六进制冒号标记法
    
    <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter19/Untitled%2010.png" class="blog-image" >
    
- 缩写
    
    <img src="https://CRYoushiwo.github.io/images/CoursesRecording/ComputerNetwork/NetworkLayer/Chapter19/Untitled%2011.png" class="blog-image" >
    
- 几种特殊地址
    - 单播地址
    - 多播地址
    - 任播地址和保留地址
    - 本地地址